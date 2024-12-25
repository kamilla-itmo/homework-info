# Домашнее задание: Планировщик задач cron
## Простое задание для тренировки 
1. Проверить наличие команды cron на линукс системе
 ```
sudo systemctl status cron
  ```
2. Если cron не установлен :
 ```
sudo apt update && sudo apt install cron
 ```
3. Далее запустите службу cron:
    ```
    sudo systemctl start cron
    sudo systemctl enable cron
     ``` 
4. Создайте простой bash-скрипт для записи текста в файл. Назовите его   ```  log_message.sh  ```:
   ```
   echo '#!/bin/bash' > ~/log_message.sh
   echo 'echo "Hello, world! $(date)" >> ~/cron_log.txt' >> ~/log_message.sh
   chmod +x ~/log_message.sh
   ```
5. Откройте редактор ``` crontab ```
6. Добавьте новую строку , которая указывает,что скрипт будет выполнятся каждую минуту.
   ```
   * * * * * ~/log_message.sh

   ```
7. Подождите 3-4 минуты , затем проверьте файл  ```cron_log.txt ```
    ```
   cat ~/cron_log.txt
    ```
   Вы должны увидеть строки с текстом Hello, world! и текущей датой.
   ## Основное задание
   ### Цель задачи :
   Создать задание,которое:
  1. Архивирует папку   ```~/my_project  ``` каждую ночь в 23:30.
  2. Сохраняет архив в папке   ```~/backups  ```.

  1. Создайте папки для проекта и резервных копий
     ```mkdir -p ~/my_project ~/backups```
  2.

   
  



