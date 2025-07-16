### Обновить версию sudo на Centos7
✅ Вариант 2: Собрать sudo из исходников

Если вам нужно, например, sudo >= 1.9.x, то проще всего:
Шаг 1. Установите зависимости:

```
sudo yum groupinstall "Development Tools"
sudo yum install make gcc wget
```

Шаг 2. Скачать последнюю версию sudo:

```
cd /usr/local/src
sudo wget https://www.sudo.ws/sudo/dist/sudo-1.9.17p1.tar.gz
sudo tar -xvzf sudo-1.9.17p1.tar.gz
cd sudo-1.9.17p1
```
Шаг 3. Собрать и установить:

```
./configure
make
sudo make install
```
    ⚠️ По умолчанию sudo будет установлен в /usr/local/bin/sudo, не затирая системный /usr/bin/sudo.

Шаг 4. Проверьте новую версию:

```
/usr/local/bin/sudo -V
```

👉 Чтобы использовать новую версию по умолчанию, можно настроить приоритет в $PATH или создать alias:
```
alias sudo='/usr/local/bin/sudo'
```


из пакетов

```
sudo yum install https://…/sudo-1.9.17-2.el7.x86_64.rpm
```
    Скачивание + установка в одном шаге. Yum сам загрузит RPM по URL и тут же поставит его.

    Автоматическое разрешение зависимостей. Если пакету чего-то не хватает, yum попытается подтянуть нужные библиотеки из ваших подключённых репозиториев.

    Учет в базе yum/DNF. Пакет попадает в кэш менеджера, остаётся история установки, работают все плюшки yum (rollback, чистка кэша, проверка GPG‑подписи и т.д.).

Когда что выбирать?

    Если вам важен контроль «чисто RPM-ом», или вы не доверяете репозиториям, — первый вариант.
```    
1	wget https://github.com/sudo-project/sudo/releases/download/v1.9.17p1/sudo-1.9.17-2.el7.x86_64.rpm && sudo rpm -Uvh sudo-1.9.17-2.el7.x86_64.rpm
```
    Если нужны удобство, автоматическое разрешение зависимостей и интеграция с системой управления пакетами — второй.
```    
2   sudo yum install https://github.com/sudo-project/sudo/releases/download/v1.9.17p1/sudo-1.9.17-2.el7.x86_64.rpm 
```



