# -Web-page-parser

Программа парсит страницы рассписания

# Описание API:

## GET: /group/:id

- **id** - id группы c сайта РГППУ
например: `мРИС-101` соответсвует id 2806  

пример запроса:
- localhost:3000/group/2806

В ответ проходит Json строка со следующими ключами (*имя* - *описание* (*пример*)):  
- **name_of_group** - Название группы ("мРИС-101")  
- **data** - Дата проведения пары ("11.03.2019")  
- **number** - порядковый номер пары ("4.")  
- **time** - время начала пары ("13:45")  
- **name** - название пары ("Командообразование и методы групповой работы") 
- **type** - тип пары (лекция, практика, лабораторная работа) ("(лаб. работа)")  
- **class_room** - номер кабинета ("0-405")  
- **name_of_pedagog** - ФИО предподователя ("Аболина Н.С.") 

## GET: /teacher/:id

- **id** - id предподователя c сайта РГППУ
например: `Аболина Наталья Семеновна` соответсвует id 1  

пример запроса:
- localhost:3000/group/1

В ответ проходит Json строка со следующими ключами (*имя* - *описание* (*пример*)):  
- **name_of_ped** - ФИО предподавателя ("Аболина Наталья Семеновна")
- **data** - Дата проведения пары ("11.03.2019")
- **number** - порядковый номер пары ("4.")
- **time** - время начала пары ("13:45")
- **name** - название пары ("Командообразование и методы групповой работы")
- **type** - тип пары (лекция, практика, лабораторная работа) ("(лаб. работа)") 
- **class_room** - номер кабинета ("0-405")
- **name_of_group** - название группы ("ПС-111")
- **pod_group** - название подгруппы (" ")

# Запуск

1. Утановить: node.js (https://nodejs.org/dist/v10.15.3/node-v10.15.3-x64.msi)  
1. установить пакетный менеджер: yarn, командой "npm i yarn -g"  
1. При первом запуске выполнить в дерриктори с проектом: "yarn install"  
1. Для запуска выполнить:
  - Для запуска в режиме разработки выполнить в директори с проектом: "yarn dev"  
  - Для запуска в режиме продакшн в дерриктори с проектом: "yarn start"  

# docker

сборка образа - `docker build -t mris/parser .`  
запуск образа - `docker run --rm -ti -p 80:80 mris/parser` 
или в фоне - `docker run --rm --name parser -d -p 80:80 mris/parser`  
запуск через compose - `docker-compose up`  
