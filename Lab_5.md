Практична робота № 5. Оперативна пам’ять.
Методичні рекомендації : https://vo.uu.edu.ua/mod/resource/view.php?id=164739
Звіт з практичної роботи №5 має бути .doc файлом і містити відповіді або скріншоти з кожного завдання.

Передумови: 
    1. Виконання Практичної роботи № 2.
    2. Виконання Практичної роботи № 4.
    3. Знайомство з Лекцією №5.
   
  ![Screenshot from 2023-01-05 13-33-18](https://user-images.githubusercontent.com/113579489/210771895-4f809df4-108f-4032-8476-6795c765b5d1.png)



Завдання №1. Дослідження віртуальної та фізичної пам'яті.
    1. Запустить віртуальну машину Ubuntu
    2. Відкрийте термінал 
    3. Виконайте команду 

ps aux


    4. У виводі команди ps aux є два поля: 

RSS - Resident Set Size – показує скільки пам’яті безпосередньо зайнято процесом в оперативній пам’яті.

VSZ - Virtual Memory Size – розмір віртуальної пам’яті зайнятою процесом.

    5. Виберіть будь-який процес.
    6. Для цього процесу порівняйте значення RSS і VSZ. 
    7. Яке із значень більше? Чому? Надайте відповідь у звіті.

![Screenshot from 2023-01-05 13-35-24](https://user-images.githubusercontent.com/113579489/210772060-ffba116f-83bb-4105-8c87-08a14ee75378.png)


Завдання №2. Збереження сторінок пам'яті на диску
    1. Відкрийте термінал 
    2. Виконайте команду 

swapon --show

    3. Команда swapon дозволяє налаштувати параметри зберігання на диску сторінок віртуальної пам’яті.
    4. Опція  - - show лише виконує вивід на екран вже налаштованих місць зберігання свопу.
    5. Який файл налаштований у вашій системі? Надайте відповідь у звіті.

![Screenshot from 2023-01-05 13-36-17](https://user-images.githubusercontent.com/113579489/210772093-1adbd009-bf23-450f-b645-95beae1e2763.png)

Завдання №3. Загальна інформація про оперативну пам'ять системи
    1. Запустить віртуальну машину Ubuntu
    2. Відкрийте термінал 
    3. Виконайте команду 
free -h
    4. Команда відображає вільну та зайняту оперативну пам'ять системи.

![Screenshot from 2023-01-05 13-36-35](https://user-images.githubusercontent.com/113579489/210772150-895e65ca-e278-4f59-b71f-215f4ac84d79.png)

    5. Зверніть увагу, що:

    1. У вас є два рядочк: Mem і Swap. Чому так? Надайте відповідь у звіті.
    2. Що використана пам'ять (used) + пам'ять що розділяють всі процеси (shared) + кеш (cache) + доступна (available) != загальній кількості пам’яті  (total).
    6. Зробіть скріншот.

![Screenshot from 2023-01-05 13-36-35](https://user-images.githubusercontent.com/113579489/210772150-895e65ca-e278-4f59-b71f-215f4ac84d79.png)

Завдання №4. Контроль за свопом. Ввімкнення/відключення свопу.
    1. Відкрийте термінал 
    2. Виконайте команду 
free -h
![Screenshot from 2023-01-05 13-36-35](https://user-images.githubusercontent.com/113579489/210772150-895e65ca-e278-4f59-b71f-215f4ac84d79.png)

    3. Зверніть увагу у вас є своп.
    4. Відключіть своп. Виконайте команду: 
sudo swapoff -a

    5. Виконайте команду 
free -h

![Screenshot from 2023-01-05 13-36-35](https://user-images.githubusercontent.com/113579489/210772150-895e65ca-e278-4f59-b71f-215f4ac84d79.png)

    6. Що змінилось після виконання команди swapoff? Надайте відповідь у звіті.
    7. Включіть своп знов:
sudo swapon -a

Завдання №5. Розподіл пам’яті по сторінках віртуальної пам’яті
    1. Відкрийте термінал 
    2. Виконайте команду 
ps aux

    3. Серед процесів виберіть будь-який, що належить вашому користувачу, і має не нульове значення віртуальної пам’яті. Наприклад процес bash.
    4. Виконайте команду відображення віртуальної пам’яті процесу 
pmap  -x [PID]
    5. Де [PID] – ідентифікатор процесу з пункту 3.

![Screenshot from 2023-01-05 13-38-28](https://user-images.githubusercontent.com/113579489/210772337-ee389a22-d4db-43a5-8b38-224799122900.png)

    6. Зробіть скріншот виводу команди.
    7. Скільки приблизно пам’яті відведено під стек [stack]? Надайте відповідь у звіті.
    8. Скільки приблизно пам’яті відведено під дані [anon]? Надайте відповідь у звіті.


