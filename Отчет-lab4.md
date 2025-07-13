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

![telegram-cloud-photo-size-2-5447510341429885224-x](https://github.com/user-attachments/assets/573543b3-cf65-4ba7-9779-0102639eb36d)

Далее создаем директорию `docker_aafire`, внутри которой создаем наш докер-файл `dockerfile`.

![telegram-cloud-photo-size-2-5418227877176012543-x](https://github.com/user-attachments/assets/49ca0a23-bff0-4e9d-adf0-2a6f89df0e22)

Внутри него прописываем следующее:

![telegram-cloud-photo-size-2-5447510341429885226-x](https://github.com/user-attachments/assets/7e9fd1ab-c4b6-43cf-9d51-8ca388b874c6)

Докер-файл устанавливает 2 пакета:

`libaa-bin` - для графической анимации в текстовом режиме

`iputils-ping` - для проверки сетевых соединений командой ping

Этот образ будет использоваться для запуска контейнеров с `aafire` и проверки сетевых соединений. Теперь строим 2 образа:

![telegram-cloud-photo-size-2-5449762141243568933-x](https://github.com/user-attachments/assets/9644cb9b-ba5d-4eda-b444-991bd748dba2)

Затем поочередно запускаем контейнеры с помощью команды `docker run -it aafire1` и `docker run -it aafire2`.

В отедельных окнах появляется интерактивная форма контейнеров (анимации огня), которую мы оставляем работать в фоновом режиме.

<img width="803" height="599" alt="81" src="https://github.com/user-attachments/assets/d74ea107-7065-415d-bc98-881463283399" />
<img width="803" height="599" alt="80" src="https://github.com/user-attachments/assets/d5b81130-2f2f-4248-b696-55de0cf17858" />

Создаем сеть `myNetwork`:

![2025-07-14 00 16 19](https://github.com/user-attachments/assets/504e7266-641f-4771-8189-becd5374b3e5)

Далее нам нужно узнать имена контейнеров:

![2025-07-14 00 28 48](https://github.com/user-attachments/assets/030e8cea-63f5-4bf5-8b1f-36122dcd9962)

Подключаем оба контейнера к нашей сети:

![2025-07-14 00 21 38](https://github.com/user-attachments/assets/73c828de-83ab-4e4f-8f29-c4e54eb4b9f2)

Узнаем IP-адреса обоих контейнеров:

![2025-07-14 00 30 21](https://github.com/user-attachments/assets/9915991a-91c3-4d55-8ca7-ed68c93e2c64)
![2025-07-14 00 31 48](https://github.com/user-attachments/assets/06d6ea5f-d834-4184-a500-529d1e4f0dd6)

И, наконец, пингуем оба контейнера. Видим, что всё успешно.

![2025-07-14 00 35 13](https://github.com/user-attachments/assets/592290b2-c4de-4953-af5e-edd52475f803)
![2025-07-14 00 36 42](https://github.com/user-attachments/assets/a29daf02-222a-4225-9ad2-306bcc401c2b)


