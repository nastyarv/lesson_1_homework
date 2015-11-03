# Домашнее задание #1

## Задание #1. Тестируем новую программу для просмотра изображений типа Instagram с новой фичей repost (далее – репост). 
### Тест-план:
#### 1. Анализ:
Кто пользователь? – любой человек, установивший на мобильное устройство программу (далее – ПО)

Зачем? – для загрузки личных фото на свою страницу, для просмотра фото других пользователей, добавление/удаление пользователей в друзья, репост чужих фото на свой страницу с помощью одного клика.

Как работает? – просмотр фото друзей в ленте новостей, загрузка личных фото и репост путем нажатия соответствующих кнопок. 

Что использует? – мобильное устройство, интернет
#### 2. Будем тестировать:
- установка и загрузка обновленного ПО
- загрузка фото
- просмотр фото в ленте новостей
- добавление/удаление пользователей в друзья
- функцию репоста (отображение на своей странице «репостнутых» фото)
- скорость загрузки фото
- скорость отображения «репостнутых» фото
- наличие в новом интерфейсе кнопки репоста
- на разных платформах (iOS, Android, WindowsPhone)
#### 3. Не будем тестировать:
- скорость установки ПО – зависит от скорости Интернета и особенностей конкретного мобильного устройства
- на разных моделях и типах мобильных устройств – добавление новой фичи не влияет на железо
#### 4. Уровни тестирования:
Системные тесты – ПО в целом
#### 5. Виды тестирования:
- Установки – проверка правильной установки и дальнейшего запуска на мобильном устройстве;
- Регрессионное – проверка на то, что добавление фичи не сократило предыдущий функционал (проверка основного функционала);
- Функциональное – проверка работы нового функционала;
- Производительность – скорость обработки данных;
- Совместимость – проверка ПО на трех самых популярных операционных системах(iOS, Android, WindowsPhone)
#### 6. Условия тестирования:
- Белый ящик – тестирование с осознанием функционала;
- Динамическое – тестирование при реальном запуске ПО;
- Позитивное – тестирование основных сценариев. 
#### 7. Заканчиваем тестирование если:
- ПО корректно установлено и запускается на трех популярных ОС;
- новая фича  и ранее реализованный функционал работают корректно;
- производительность соответствует заявленному в документации ПО уровню качества. 

## Задание #2. 
### Найденные баги :
1.	Space in the middle ( «Nastya Anna»)
2.	Space values at the end ( «Nastya »)
3.	Space values at the begining ( « Nastya»)
4.	Empty value ( «»)
5.	Space ( «        »)
6.	More than maximum values ( «kkkkkkkkkkkkkkkkkkkkkkkkkkkkkkk» - 31 символ )
7.	Non ASCII ( «Настя» - кириллица)
8.	Average value ( «Alla» - среднее значение)
9.	Minimum value ( «a» - минимальное значение)
10.	Maximum values ( «kkkkkkkkkkkkkkkkkkkkkkkkkkkkkk» - 30 символов )
11.	Other chars then alphabetic ( «25624»)

### Баг-репорт «Empty»
1. Предусловия: 
   1.1. Открыть страницу с формой регистрации
   1.2	Заполнить поля Country, Email, Last Name соответственно Norway, me@whatyouknow.com, Gheorghe
2. Шаги:
   2.1 Поле First Name оставить пустым
   2.2 Нажать кнопку Submit, то есть отправить запрос на обработку 
3. Ожидаемый результат:
   3.1 Сообщение об ошибке «Empty values»
  3.2 Отказ в регистрации
4. Реальный результат:
   4.1 Регистрация успешно завершается
   4.2 Поле First Name остается пустым

### Баг-репорт «Space»
1. Предусловия: 
   1.1. Открыть страницу с формой регистрации
   1.2	Заполнить поля Country, Email, Last Name соответственно Norway, me@whatyouknow.com, Gheorghe
2. Шаги:
   2.1 В Поле First Name ввести 5 пробелов
   2.2 Нажать кнопку Submit, то есть отправить запрос на обработку 
3. Ожидаемый результат:
   3.1 Сообщение об ошибке «Space»
   3.2 Отказ в регистрации
4. Реальный результат:
   4.1 Регистрация успешно завершается
   4.2 Поле First Name заполняется пробелами

### Баг-репорт «More then MAX»
1. Предусловия: 
   1.1. Открыть страницу с формой регистрации
   1.4	Заполнить поля Country, Email, Last Name соответственно Norway, me@whatyouknow.com, Gheorghe
2. Шаги:
   2.1 В Поле First Name ввести «kkkkkkkkkkkkkkkkkkkkkkkkkkkkkkk» - 31 символ
   2.2 Нажать кнопку Submit, то есть отправить запрос на обработку 
3. Ожидаемый результат:
  3.1 Сообщение об ошибке «More than maximum values» 
  3.2 Отказ в регистрации
4. Реальный результат:
  4.1 Регистрация успешно завершается
  4.2 Поле First Name заполняется символами «kkkkkkkkkkkkkkkkkkkkkkkkkkkkkkk».

## Задание #3. 
Действительно, мнения о роли тестировщика в процессе создания ПО расходятся. Мои рассуждения будут по методу «от противного». ### Пример 1. Если представить, что в IT-компании нет тестировщиков и каждый отдел самостоятельно занимается модульным тестированием. 
Плюсы: нет необходимости в новых сотрудниках. 
Минусы: увеличивается срок разработки; могут быть заторможены последующие стадии разработки; нет видения конечного результата; нет возможности интеграционного и системного тестирования. 
### Пример 2. В каждой команде разработчиков выделить одного сотрудника для тестирования. 
Плюсы: нет необходимости в новых сотрудниках. 
Минусы: нет видения конечного результата; нет возможности интеграционного и системного тестирования. 
Делая вывод на основе двух примеров, могу предположить, что материальная выгода от сокращения персонала может повлечь за собой много трудностей. На мой взгляд, в каждой уважающей себя IT-компании должны быть тестировщики как отдельная, уважаемая и незаменимая команда. 
=)

## Задание 4. 
Социотехнические системы – это рабочая система, состоящая из технической подсистемы (устройства, инструменты, технологии и тд.), социальной подсистемы ( сотрудники, служащие, пользователи и тд) и подсистемы среды.  
Следовательно, ошибки в социотехнических системах могут возникать из-за двух глобальных факторов:
1.	Человеческий фактор  - ошибочные действия человека в процессе взаимодействия с техникой ( ошибки в социальной подсистеме)
2.	Технические неполадки – сбои в ПО, дефекты железа (ошибки в технической подсистеме). 



