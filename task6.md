task6
services:
  database:
    container_name: db
    image: mariadb:10.11
    restart: always
    ports:
      - "3306:3306"
    environment:
      MARIADB_DATABASE: testdb
      MARIADB_USER: test
      MARIADB_PASSWORD: P@ssw0rd
      MARIADB_ROOT_PASSWORD: root
#на пользователях ДЭ пароль будет другой учитывайте это а не слепо копируйте
  app:
    container_name: tespapp
#название контейнера правильное, в задании написано, что основной контейнер testapp должен называться tespapp
#при дальнейшей настройки docker это может ввести вас в заблуждение
    image: site:latest
    restart: always
    ports:
      - "8080:8000"
    environment:
      DB_TYPE: maria
      DB_HOST: 192.168.3.2
      DB_PORT: "3306"
      DB_NAME: testdb
      DB_USER: test
      DB_PASS: P@ssw0rd
    depends_on:
      - database
