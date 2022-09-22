# Lab2_Operating_System

1. [Установка операційної системи Ubuntu у Virtualbox](https://github.com/IllyaMarchevskyi/Lab2_Operating_System/blob/main/README.md#%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B0-%D0%BE%D0%BF%D0%B5%D1%80%D0%B0%D1%86%D1%96%D0%B9%D0%BD%D0%BE%D1%97-%D1%81%D0%B8%D1%81%D1%82%D0%B5%D0%BC%D0%B8-ubuntu-%D1%83-virtualbox)
2. [Установка самої операційної системи Ubuntu](https://github.com/IllyaMarchevskyi/Lab2_Operating_System/blob/main/README.md#%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B0-%D1%81%D0%B0%D0%BC%D0%BE%D1%97-%D0%BE%D0%BF%D0%B5%D1%80%D0%B0%D1%86%D1%96%D0%B9%D0%BD%D0%BE%D1%97-%D1%81%D0%B8%D1%81%D1%82%D0%B5%D0%BC%D0%B8-ubuntu)
3. [Виконання базових команд](https://github.com/IllyaMarchevskyi/Lab2_Operating_System/blob/main/README.md#%D0%B2%D0%B8%D0%BA%D0%BE%D0%BD%D0%B0%D0%BD%D0%BD%D1%8F-%D0%B1%D0%B0%D0%B7%D0%BE%D0%B2%D0%B8%D1%85-%D0%BA%D0%BE%D0%BC%D0%B0%D0%BD%D0%B4)
4. [Оновити ядро системи, встановивши пакет підтримки повного екрану](https://github.com/IllyaMarchevskyi/Lab2_Operating_System/blob/main/README.md#%D0%BE%D0%BD%D0%BE%D0%B2%D0%B8%D1%82%D0%B8-%D1%8F%D0%B4%D1%80%D0%BE-%D1%81%D0%B8%D1%81%D1%82%D0%B5%D0%BC%D0%B8-%D0%B2%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%B8%D0%B2%D1%88%D0%B8-%D0%BF%D0%B0%D0%BA%D0%B5%D1%82-%D0%BF%D1%96%D0%B4%D1%82%D1%80%D0%B8%D0%BC%D0%BA%D0%B8-%D0%BF%D0%BE%D0%B2%D0%BD%D0%BE%D0%B3%D0%BE-%D0%B5%D0%BA%D1%80%D0%B0%D0%BD%D1%83)
5. [Помилки які трапляються частіше всього](https://crashbox.ru/solving-problems/virtualbox-gives-an-error-what-to-do-if-you-can-not-open-a-session-for-a-virtual-machine/)


## Установка операційної системи Ubuntu у Virtualbox

Так як ми на попередній лабораторній встановили [Virtualbox](https://github.com/IllyaMarchevskyi/Lab1_Operating_System#lab1_operating_system) сьогодні ми зразу перейдемо до встановлення <b>Ubuntu</b>

Скачати іso образ можна прейшовши на офіційний сайт [Ubuntu_download](https://ubuntu.com/download/desktop)

Створіть нову віртуальну машину 

![Screenshot from 2022-09-15 10-29-17](https://user-images.githubusercontent.com/113579489/190342384-12cbb539-9eb1-409b-aeb3-d7c2bddc692d.png)

Називаємо машину

![Screenshot from 2022-09-15 10-31-08](https://user-images.githubusercontent.com/113579489/190342802-d6719024-d129-4b4f-8949-a7c3dddcd9dc.png)

Вибираємо скільки операційної пам'яті ми можемо виділити(я буду виділяти 2гб)

![Screenshot from 2022-09-15 10-32-17](https://user-images.githubusercontent.com/113579489/190342996-a49c1bf8-f0c8-416f-bcd5-13d24602bf14.png)

Зараз ми вирішимо скільки місця буде виділено на жосткому диску для встановлення операційної системи( я буду виділяти 20гб )

![Screenshot from 2022-09-15 10-33-57](https://user-images.githubusercontent.com/113579489/190343399-4904d1a9-8801-463f-a02e-bb2415d88ca6.png)

Натискаємо Create -> Next(вибираємо все по default) -> Next(вибираємо все по default) 
А тут ми вже вибирамо скільки місця ми готові виділити

![Screenshot from 2022-09-15 10-42-07](https://user-images.githubusercontent.com/113579489/190345271-a55e07b1-a749-4147-a7ea-24e60cc1d26e.png)

Переходимо в налаштування `Settings`

![Screenshot from 2022-09-15 10-45-18](https://user-images.githubusercontent.com/113579489/190345940-00ba73ea-2c8f-4be6-b92e-d000d28c092d.png)

Вибираємо Advnced і там вибираємо Bidirectional

![Screenshot from 2022-09-15 10-48-49](https://user-images.githubusercontent.com/113579489/190346918-74a125e3-7da9-4a79-b893-0d8961dd50ff.png)

Далі переходимо у розіділ Storage, натискаємо на Empty, а потім на іконку  

![Screenshot from 2022-09-15 10-54-59](https://user-images.githubusercontent.com/113579489/190347921-66f8f867-eb18-482d-9d85-44dd385c8e9d.png)

Додаємо ваш  iso образ. Після цього випобачити замість Empty -> назва iso образу

![Screenshot from 2022-09-15 10-58-11](https://user-images.githubusercontent.com/113579489/190348591-ce3d8542-53fc-4343-a5ba-ec91c6a4df4c.png)

## Установка самої операційної системи Ubuntu

Запускаємо операційну ситему

![Screenshot from 2022-09-15 11-02-11](https://user-images.githubusercontent.com/113579489/190349439-412645da-a55d-4b40-95cb-df81a827a95e.png)

Я вибиру гарфічний спосіб установлення. 
Тепер потрібно трішки зачикати.
Ось що ви побачите після загрузки

![Screenshot from 2022-09-15 11-09-40](https://user-images.githubusercontent.com/113579489/190350984-0dc99442-7e4d-40fb-9930-7576b8fee2d3.png)

Вибираємо мову я вибиру English i Install Ubuntu.

![Screenshot from 2022-09-15 11-12-05](https://user-images.githubusercontent.com/113579489/190351428-b0a091eb-72b3-4ae0-a8fd-b28f4546fe00.png)

Підтвержуємо все по default.
В кінці вам потрібно придумати пароль і user_name

![Screenshot from 2022-09-15 11-22-15](https://user-images.githubusercontent.com/113579489/190353646-617ce5a5-eb07-4aac-841c-529fd006ffe4.png)

Після завершення установки у вас перезавантажиться Ubuntu.
І процес встановлення завершиться.
<b>Вітаю ви встановли Ubuntu.</b>


## Виконання базових команд

Коли Ubuntu запуститься вам потрібно ініцілізуватися

![Screenshot from 2022-09-16 17-17-31](https://user-images.githubusercontent.com/113579489/190662686-bba4a03d-35e6-4f49-837b-120998ca21ad.png)

Відкриваємо термінал такою послідовністю команд Cntr + Alt + T

![Screenshot from 2022-09-16 17-31-03](https://user-images.githubusercontent.com/113579489/190663573-b23d59c9-5f14-410b-a30d-bb52517ef205.png)


Тепер нам потрібно увести такі команди 

Показує наше росташування:
```
pwd

```
Показує тещо знаходиться в даному файлі з додатковими уточненями:
```
ls -al
``` 

![Screenshot from 2022-09-16 17-31-03](https://user-images.githubusercontent.com/113579489/190663573-b23d59c9-5f14-410b-a30d-bb52517ef205.png)


## Оновити ядро системи, встановивши пакет підтримки повного екрану

Встановити програмне забезпечення, що підтримує режим повного екрану:

Тепер нам потрібно отримати увести таку програму
```
sudo apt install build-essential dkms linux-headers-$(uname -r)
```

