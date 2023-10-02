# Отчет по практиечской работе номер-2 "Идентификация и аутентификация"

## Задача

В данном задании выполнены следующие шаги:

1. Создана виртуальная машина на базе ОС Debian 12.
2. Создан пользователь `super-{Pankov.E.R}` и наделен привилегиями суперпользователя.
3. Создана группа `group-{Adm}`.
4. Добавен пользователь `super-{Pankov.E.R}` в группу `group-{Adm}`.
5. Проверено наличие пользователя в группе.
6. Создан пользователь `user-{Pankov.E.R}` и добавен в группу `group-{Adm}`.
7. Наделен полномочиями пользователь `user-{Pankov.E.R}` по созданию и удалению файлов в домашнем каталоге пользователя `super-{Pankov.E.R}` с использованием механизма разграничения доступа `chmod`.
8. Продемонстрирована работа механизмов разграничения доступа.

## Шаги выполнения

```bash
# Шаг 2
root@Debian:~# sudo useradd super-{Pankov.E.R}
root@Debian:~# passwd super-{Pankov.E.R}
root@Debian:~# usermod -aG sudo super-{Pankov.E.R}

# Шаг 3
root@Debian:~# groupadd group-{Adm}

# Шаг 4
root@Debian:~# usermod -aG group-{Adm} super-{Pankov.E.R}

# Шаг 5
root@Debian:~# groups super-{Pankov.E.R}

# Шаг 6
root@Debian:~# useradd user-{Pankov.E.R}
root@Debian:~# usermod -aG group-{Adm} user-{Pankov.E.R}

# Шаг 7
root@Debian:~# chmod 770 /home/super-{Pankov.E.R}
root@Debian:~# chown super-{Pankov.E.R}:group-{Adm} /home/super-{Pankov.E.R}

# Шаг 8
$ su user-{Pankov.E.R}
$ touch /home/super-{Pankov.E.R}/test_file.txt
$ rm /home/super-{Pankov.E.R}/test_file.txt

```


[Скриншот 1 - Команды в терминале для шага номер-2 ]
![Скриншот 1 - Команды в терминале ](https://i.imgur.com/qo81Qcv.png)
[Скриншот 2 - Команды в терминале для шага номер-3 ]
![Скриншот 2 - Команды в терминале ](https://imgur.com/a/SozH0lZ)
[Скриншот 3 - Команды в терминале для шагов номер-4 и 5 ]
![Скриншот 3 - Команды в терминале ](https://imgur.com/a/K2XCH21)
[Скриншот 4 - Команды в терминале для шага номер-6]
![Скриншот 4 - Команды в терминале ](https://imgur.com/a/oSVBraB)
[Скриншот 5 - Команды в терминале для шага номер-7]
![Скриншот 5 - Команды в терминале ](https://imgur.com/a/7elzVhZ)
[Скриншот 6 - Команды в терминале для шага номер-8]
![Скриншот 6 - Команды в терминале ]([https://imgur.com/a/lEZhesc](https://imgur.com/a/lEZhesc)https://imgur.com/a/lEZhesc)
