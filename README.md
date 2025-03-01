# Сервис взаимодействия с сервером электронной почты Apache James

Для запуска проекта необходимо:

1. Загрузить JAR реализации JDBC драйвера для PostgreSQL;

2. Сгенерировать keystore командой: `keytool -genkey -alias james -keyalg RSA -storepass 'james72laBalle' -keystore ./docker/mail-server/keystore -dname "CN=yourname, C=ru" -validity 365`, где значения параметров `CN` (имя и фамилия) и `C` (двухбуквенных код страны) необходимо заменить на ваши, или вообще убрать, оставив в качестве значения именованного параметра `-dname` пустую строку;

3. Перейти в коррень проекта и выполнить команду `docker compose up -d`.