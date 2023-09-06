# Домашнее задание к занятию «Disaster Recovery. FHRP и Keepalived» - Romashkova Alina

### Задание 1
- Дана [схема](1/hsrp_advanced.pkt) для Cisco Packet Tracer, рассматриваемая в лекции.
- На данной схеме уже настроено отслеживание интерфейсов маршрутизаторов Gi0/1 (для нулевой группы)
- Необходимо аналогично настроить отслеживание состояния интерфейсов Gi0/0 (для первой группы).
- Для проверки корректности настройки, разорвите один из кабелей между одним из маршрутизаторов и Switch0 и запустите ping между PC0 и Server0.
- На проверку отправьте получившуюся схему в формате pkt и скриншот, где виден процесс настройки маршрутизатора.

#### Результат

- Router 1, 2 config:

![Router 1](https://github.com/ARMSHK/HW-SYS-19/blob/main/img/Router_1_Config.png)

![Router 2](https://github.com/ARMSHK/HW-SYS-19/blob/main/img/Router_2_Config.png)

- ICMP from PC to Server:

![ICMP](https://github.com/ARMSHK/HW-SYS-19/blob/main/img/ICMP_Route_Succcessful.png)

### Задание 2
- Запустите две виртуальные машины Linux, установите и настройте сервис Keepalived как в лекции, используя пример конфигурационного [файла](1/keepalived-simple.conf).
- Настройте любой веб-сервер (например, nginx или simple python server) на двух виртуальных машинах
- Напишите Bash-скрипт, который будет проверять доступность порта данного веб-сервера и существование файла index.html в root-директории данного веб-сервера.
- Настройте Keepalived так, чтобы он запускал данный скрипт каждые 3 секунды и переносил виртуальный IP на другой сервер, если bash-скрипт завершался с кодом, отличным от нуля (то есть порт веб-сервера был недоступен или отсутствовал index.html). Используйте для этого секцию vrrp_script
- На проверку отправьте получившейся bash-скрипт и конфигурационный файл keepalived, а также скриншот с демонстрацией переезда плавающего ip на другой сервер в случае недоступности порта или файла index.html

#### Результат

- Keepialived redirectiom from 10.0.2.16 (main) to 10.0.2.15 (reserv)

![Keepalived_Redirection](https://github.com/ARMSHK/HW-SYS-19/blob/main/img/Keepalived_Redirection.png)
