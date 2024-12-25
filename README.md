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
      Архивирует папку   ```~/my_project  ``` каждую ночь в 23:30.
   
      Сохраняет архив в папке   ```~/backups  ```.

  1. Создайте папки для проекта и резервных копий
     ```mkdir -p ~/my_project ~/backups```
  2. Создайте скрипт для архивирования
    ``` nano ~/backup_project.sh ```
  3. Вставьте код
 ```    #!/bin/bash
     tar -czf ~/backups/my_project_$(date +\%Y-\%m-\%d).tar.gz ~/my_project
 ```
  4. сделайте скрипт исполняемым
      ```
       chmod +x ~/backup_project.sh
      ```
  5. Далее откройте crontab , при помощи строки  ```crontab -e ``` и добавьте строку   ``` 30 23 * * * ~/backup_project.sh ```
  6.  Дождитесь запуска задания или выполните его вручную для проверки:
      ```
      ~/backup_project.sh
      ```
   ## Ссылки на материалы

   [Официальная документация CRON](https://help.ubuntu.ru/wiki/cron)
   
   [Введение в планировщик CRON](https://timeweb.com/ru/community/articles/chto-takoe-cron)
   
   [Команды Linux для работы с CRON](https://www.hostcms.ru/documentation/server/crontab/)
    
       
 




   
  



