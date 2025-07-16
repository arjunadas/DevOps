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
