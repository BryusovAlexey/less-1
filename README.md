# less-1
Обновить ядро в базовой системе
создание аккаутна на  github и vagrant cloud
создание файла с кодом vagrantfile. приклеплен в github
vagrant ssh подключение к виртуальному машине
проверка ядра текущей системы
alex-linux@alexlinux:~/linux-vm$ vagrant ssh
[vagrant@kernel-update ~]$ uname -r
4.18.0-277.el8.x86_64
загрузка новых ядер из репозитория
[vagrant@kernel-update ~]$ sudo yum install -y https://www.elrepo.org/elrepo-release-8.el8.elrepo.noarch.rpm
Failed to set locale, defaulting to C.UTF-8
CentOS Stream 8 - AppStream                                                                     782 kB/s |  27 MB     00:35    
CentOS Stream 8 - BaseOS                                                                        1.1 MB/s |  26 MB     00:24    
CentOS Stream 8 - Extras                                                                         24 kB/s |  18 kB     00:00    
elrepo-release-8.el8.elrepo.noarch.rpm                                                          9.3 kB/s |  13 kB     00:01    
[vagrant@kernel-update ~]$ uname -r
6.1.6-1.el8.elrepo.x86_64
[vagrant@kernel-update ~]$ 
обновить конфигурацию загрузчика:
sudo grub2-mkconfig -o /boot/grub2/grub.cfg
Generating grub configuration file ...
done
[vagrant@kernel-update ~]$ sudo grup2-set-default 0
sudo: grup2-set-default: command not found
#[vagrant@kernel-update ~]$ sudo grub2-set-default 0
#перезагрузка ВМ
#[vagrant@kernel-update ~]$ sudo reboot
#создание образа в  packer
#alex-linux@alexlinux:~/linux-vm$ mkdir packet
#alex-linux@alexlinux:~/linux-vm$ cd packet
#alex-linux@alexlinux:~/linux-vm/packet$ ls -l
#итого 0
#alex-linux@alexlinux:~/linux-vm/packet$ ls -l
#итого 4
#-rw-rw-r-- 1 alex-linux alex-linux 2147 янв 15 03:02 centos.json
#alex-linux@alexlinux:~/linux-vm/packet$ mkdir http
#alex-linux@alexlinux:~/linux-vm/packet$ cd http
#alex-linux@alexlinux:~/linux-vm/packet/http$ touch ks.cfg
#alex-linux@alexlinux:~/linux-vm/packet/http$ ls -l
#итого 0
#-rw-rw-r-- 1 alex-linux alex-linux 0 янв 15 03:05 ks.cfg
#создание скриптов

#проверка работы вм в виртуалбокс

#загрузка всех данных в github
