# Отчет по практиечской работе номер-2 "Идентификация и аутентификация"

## Задача

В данном задании выполнены следующие шаги:

1. Создана виртуальная машина на базе ОС Debian 12.
2. Создан пользователь `super-{Kozlov.F.S}` и наделен привилегиями суперпользователя.
3. Создана группа `group-{Miread}`.
4. Добавен пользователь `super-{Kozlov.F.S}` в группу `group-{Miread}`.
5. Проверено наличие пользователя в группе.
6. Создан пользователь `user-{Kozlov.F.S}` и добавен в группу `group-{Miread}`.
7. Наделен полномочиями пользователь `user-{Kozlov.F.S}` по созданию и удалению файлов в домашнем каталоге пользователя `super-{Kozlov.F.S}` с использованием механизма разграничения доступа `chmod`.
8. Продемонстрирована работа механизмов разграничения доступа.

## Шаги выполнения

```bash
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

```


[Скриншот 1 - Команды в терминале для представленных выше шагов ]

![Скриншот 1 - Команды в терминале ](https://i.imgur.com/rjZxR1q.png)
