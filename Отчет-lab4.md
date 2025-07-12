# Лабораторная работа №4

Для начала нам нужно установить докер. Прописываем следующие команды:
```bash
sudo apt update
sudo apt install apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"
sudo apt update
apt-cache policy docker-ce
sudo apt install docker-ce
sudo systemctl status docker
```
Видим `active`, значит, всё успешно:

![telegram-cloud-photo-size-2-5418227877176012533-y](https://github.com/user-attachments/assets/e6b575d4-d8e1-40b9-b3a2-893f346cb147)

Далее создаем директорию `docker_aafire`, внутри которой создаем наш докер-файл `dockerfile`.

![telegram-cloud-photo-size-2-5418227877176012543-x](https://github.com/user-attachments/assets/49ca0a23-bff0-4e9d-adf0-2a6f89df0e22)

Внутри него прописываем следующее:

![telegram-cloud-photo-size-2-5418227877176012538-x](https://github.com/user-attachments/assets/627b2c23-9fd8-44ea-bef5-fa91e04d1c37)

Докер-файл устанавливает 2 пакета:

`libaa-bin` - для графической анимации в текстовом режиме

`iputils-ping` - для проверки сетевых соединений командой ping

Этот образ будет использоваться для запуска контейнеров с `aafire` и проверки сетевых соединений. Теперь строим 2 образа:

![telegram-cloud-photo-size-2-5418227877176012544-y](https://github.com/user-attachments/assets/c381f72f-83ad-47c9-bfd5-d153c02c7e67)

Затем поочередно запускаем контейнеры с помощью команды `docker run -it aafire1` и `docker run -it aafire2`.

В отедльных окнах появляется интерактивная форма контейнеров (анимации огня), которую мы оставляем работать в фоновом режиме.

![telegram-cloud-photo-size-2-5417962078829933648-y](https://github.com/user-attachments/assets/ed08e8d1-d37a-46ef-94a8-f7d699243bb1)

![telegram-cloud-photo-size-2-5418227877176012567-y](https://github.com/user-attachments/assets/0f4c35ce-4baa-4377-b6d3-52f91de69505)

Создаем сеть `myNetwork`:

![telegram-cloud-photo-size-2-5417847656606199221-y](https://github.com/user-attachments/assets/c4fb4b5f-ec38-4946-bf62-3e4b71c434dd)

Далее нам нужно узнать имена контейнеров:

![telegram-cloud-photo-size-2-5418227877176012628-y](https://github.com/user-attachments/assets/35fb2eaf-8403-4444-82fc-6e15d4458fbe)






