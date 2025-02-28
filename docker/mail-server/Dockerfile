FROM apache/james:jpa-3.8.2

COPY ./james-database.properties /root/conf/james-database.properties
COPY ./keystore /root/conf/keystore
COPY ./jars/postgresql-42.7.5.jar /root/libs/james-jdbc-driver.jar

ARG DATABASE_PASSWORD
RUN sed -i "s/\${DATABASE_PASSWORD}/$DATABASE_PASSWORD/g" /root/conf/james-database.properties

EXPOSE 587

ENTRYPOINT ["java", "-Dlogback.configurationFile=/root/conf/logback.xml", "-Dworking.directory=/root/", "-Djdk.tls.ephemeralDHKeySize=2048", "-Dextra.props=/root/conf/jvm.properties", "-cp", "/root/resources:/root/classes:/root/libs/*", "org.apache.james.JPAJamesServerMain" ]