# INT-4_Task_1-another-
Этот репозиторий для первого задания, настройки с помощью ролей


Всем машинам стоит установить статический IP-адрес. 

## Окружение

1. **Виртуальная машина с Debian**
2. **Запуск playbook Ansible происходит с Kali Linux**


## Необходимые команды для запуска Ansible:


Установим python3

```
sudo apt update
sudo apt-get install python3
sudo update-alternatives --install /usr/bin/python python /usr/bin/python3 2
```

Установка pip3 и ansible

```
sudo apt install python3-pip
pip3 install ansible
```

Укажем в переменной PATH путь до ansible
```
export PATH=$PATH:/home/user/.local/bin
```

Ввести команду:

```
sudo apt-get install sshpass
```
### Что изменить:

Поменять файл `inventory` согласно своим данным(IP-адреса и пользователей).


## Команда для запуска playbook:

```bash
ansible-playbook main_play.yml
```

## Необходимые настройки Debian машин для запуска Ansible:

1. Добавить нового пользователя "ansible". (Имя пользователя можно поменять, главное указать его затем в inventory)
2. Добавить строку в /etc/sudoers:

```
ansible ALL=(ALL:ALL) NOPASSWD:ALL
```
3. Установить сервер и клиент OpenSSH и запустить:

```
sudo apt update
sudo apt install openssh-server openssh-client
sudo systemctl enable ssh
sudo systemctl start ssh
```

# Реализуемый функционал playbook:

1. Автообновление
2. Установка базовых пакетов:
   
   2.1. vim
   
   2.2. git
   
   2.3. curl
   
   2.4. wget
   
   2.5. htop
   
   2.6. net-tools
   
   2.7. python3

3. Установка Fail2ban
4. Установка и настройка firewall
5. Установка postgresql-16 


