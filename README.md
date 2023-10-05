# TOIB-PR2-Kozlov
В данном задании выполнены следующие шаги:

    Создана виртуальная машина на базе ОС Debian 12.
    Создан пользователь super-{Kuzina.A.S} и наделен привилегиями суперпользователя.
    Создана группа group-{Miread}.
    Добавен пользователь super-{Kuzina.A.S} в группу group-{Miread}.
    Проверено наличие пользователя в группе.
    Создан пользователь user-{Kuzina.A.S} и добавен в группу group-{Miread}.
    Наделен полномочиями пользователь user-{Kuzina.A.S} по созданию и удалению файлов в домашнем каталоге пользователя super-{Kuzina.A.S} с использованием механизма разграничения доступа chmod.
    Продемонстрирована работа механизмов разграничения доступа.

Шаги выполнения

# Шаг 2
root@Debian:~# sudo useradd super-{Kozlov.F.S}
root@Debian:~# passwd super-{Kozlov.F.S}
root@Debian:~# usermod -aG sudo super-{Kozlov.F.S}

# Шаг 3
root@Debian:~# groupadd group-{Miread}

# Шаг 4
root@Debian:~# usermod -aG group-{Miread} super-{Kozlov.F.S}

# Шаг 5
root@Debian:~# groups super-{Kozlov.F.S}

# Шаг 6
root@Debian:~# useradd user-{Kozlov.F.S}
root@Debian:~# usermod -aG group-{Miread} user-{Kozlov.F.S}

# Шаг 7
root@Debian:~# chmod 770 /home/super-{Kozlov.F.S}
root@Debian:~# chown super-{Kozlov.F.S}:group-{Miread} /home/super-{Kozlov.F.S}

# Шаг 8
$ su user-{Kozlov.F.S}
$ touch /home/super-{Kozlov.F.S}/test_file.txt
$ rm /home/super-{Kozlov.F.S}/test_file.txt

[Скриншот 1 - Команды в терминале для представленных выше шагов ]

Скриншот 1 - Команды в терминале 
