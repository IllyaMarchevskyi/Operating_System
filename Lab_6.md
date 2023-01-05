Практична робота № 6. Створення утиліти збору інформації щодо структури використання оперативної пам’яті процесом.
Методичні рекомендації : https://vo.uu.edu.ua/mod/resource/view.php?id=164739
Звіт з практичної роботи №6 має бути .doc файлом і містити відповіді або скріншоти з кожного завдання.

Передумови: 
    1. Виконання Практичної роботи № 5
Завдання №1. Створення робочого каталогу
    1. Запустить віртуальну машину Ubuntu
    2. Відкрийте термінал 
Виконайте команду створення каталогу mkdir

mkdir scripts

    3. Переконайтеся, що каталог був створений 

ls -la

    4. Перейдіть у робочий каталог
cd scripts

    5. Переконайтеся що ви знаходитесь у каталозі scripts
pwd 
    6. У виводі команди має бути /scripts

![Screenshot from 2023-01-05 13-45-33](https://user-images.githubusercontent.com/113579489/210773821-b94b97cc-c9bb-4a67-ae88-a62348c5312b.png)


Завдання №2. Створення текстового скріпта
    1. Відкрийте текстовий редактор 

![image](https://user-images.githubusercontent.com/113579489/210773854-225a5ec0-9116-4291-aa99-a3566a4e8385.png)

    2. Додайте код тестового скріпта: 
#!/bin/bash
mydir=$(pwd)
echo $mydir
    3. Результат має бути таким:

![image](https://user-images.githubusercontent.com/113579489/210773871-36c1e38d-6d43-47fb-9e8e-30510dc13708.png)

    4. Збережіть файл у робочому каталозі scripts із Завдання №1.
    5. Назва файлу my_pwd
    6. Зробіть файл виконуваним. Для цього виконайте команду: 

chmod +x my_pwd

    7. Переконайтеся, що атрибути файу стали “x”

![image](https://user-images.githubusercontent.com/113579489/210773907-aab65ab8-0391-4590-8b91-925cc0305ab5.png)

    8. Запустіть скріпт: 

./my_pwd

    9. Результати виконання команди мають співпадати з результатами із пунтку 5 Завдання №1 даної Практичної роботи. 
    10. Зробіть скріншот.

![Screenshot from 2023-01-05 13-45-46](https://user-images.githubusercontent.com/113579489/210774009-6a5cbec9-8524-4932-9010-77561fc48831.png)


Завдання №3. Підготовка для аналізу використання пам’яті 
    1. У Практичній роботі №5 ми використовували команду pmap.
    2. Оберіть будь-який процес, наприклад bash
ps  aux | grep bash

![Screenshot from 2023-01-05 13-47-37](https://user-images.githubusercontent.com/113579489/210774052-78e5fe43-5683-4c78-a329-14d282975bec.png)

    3. Давайте відфильтруємо лише ті елементи що містять дані:

pmap -x {PID} | grep anon 

    4. Давайте збережемо вивід цієї команди у файл 

pmap -x {PID} | grep anon > tmp

    5. Перевіримо вміст файлу tmp:

cat tmp

    6. Мають бути лише елементи з анонимним типом даних.
    7. Зробіть скріншот. 
    8. Там же чином, ми можем відфільтрувати дані для стеку:

pmap -x {PID} | grep stack > tmp

    9. Та дані для коду:

pmap -x {PID} | grep -Ev “anon|stack” > tmp

    10.  Зверніть увагу що у п.9 ми виключили з результатів записи, що містять anon aбо stack.


Завдання №4. Обробка текстових даних.
    1. Дані виводу пункту 9 Завдання №3 містять колонки з числами, які неохідно скласти, або отримати суму пам'яті що використовується процесом.
    2. Для таких цілей  використовують команду awk.
    3. Виконайте команду: 

awk -F “ “ ‘{Total=Total + $2} END {print “Total is:” Total }’ tmp

де, 
awk -F “ “   - виклик команди з атрибутом -F (форматування) і пробілом  “ “ означає що наши дані розділені пробілами;

‘{Total=Total + $2} END {print “Total is:” Total }’  - логіка того що необхідно зробити і як опрацювати результат. В даному випадку у змінну Total додається значення колонки 2.
Результат виводиться на екран за допомогою команди print;

tmp – файл, що містить дані, які будуть опрацьовані.

    4.  Виконання має повернути результат на зразок наступного:

![image](https://user-images.githubusercontent.com/113579489/210774113-fe01fe86-379f-481b-9e3b-100abe422b5e.png)


    5. В Зробіть скріншот.

Завдання №5. Створення утиліти збору інформації щодо структури використання оперативної пам’яті процесом.
    1. Створіть новий файл process_memory_stat
    2. Зробіть його виконуваним 
chmod +x process_memory_stat
    3. Перевірте що він має атрибут виконуваного файлу «х»:
ls -la

![image](https://user-images.githubusercontent.com/113579489/210774134-5d9ef0b6-cd96-4189-9a3d-0f81cd73e15c.png)


    4. Використовуючи знання з попередніх завдань, давайте підготуємо скріпт.
    5. Логіка виконання скріпта:
    1. Використовуючи команду pmap зберігти у файл tmp інформацію по використанню сегмента даних (рядок 5 скріпта) процесом.
    2. Підрахувати сумму значень у 3 колонці (RSS), що представляє собою використання оперативної пам’яті процесом (рядок 7 скріпта).   
    3. Повторити ці дії для сегменту, що зберігає стек (рядки 9-11) та сегменту коду програми (13-15)
    4. Після цього вивести результати на екран користувача (рядки 18-21).  

![image](https://user-images.githubusercontent.com/113579489/210774160-3b81efff-2e67-443a-a17d-1052360de49c.png)

    6. Приклад використання:

./process_memory_stat {PID}           

![image](https://user-images.githubusercontent.com/113579489/210774182-67ccfd2b-222e-4ba2-b309-b527078633d7.png)


    7. Зверніть увагу, що для того аби скріпт міг приймати на вхід параметр {PID} ми додали у скріпт змінну pid, що зберігає значення вхідного параметра (рядок 3 скріпта).
    8. Запустіть ./process_memory_stat для вашого процесу. Зробіть скріншот.