

#  Потоки і процеси

1. [Підготовка середовища]()
2.

## Підготовка середовища (Прогама встановлюється лише на Windows)

Встановлюємо ProcessExplorer:
* Cилка на сайт - [Оriginal site](https://learn.microsoft.com/uk-ua/sysinternals/downloads/process-explorer)
* Силка зразу на встановлення - [Dowloand ProcessExplorer](https://download.sysinternals.com/files/ProcessExplorer.zip)

Розархівовуємо та встановлюємо ProcessExplorer.

![image](https://user-images.githubusercontent.com/113579489/191675520-0c52346f-512a-43a1-a0cf-93f93990dddb.png)

Запускаємо ProcessExplorer procexp.exe

![image](https://user-images.githubusercontent.com/113579489/191675413-fa992512-21cc-4278-bb41-22f91d250d42.png)

# Процеси у Windows

Запустіть Chrome. Зверніть увагу що Chrome запускає кілька процесів.

![image](https://user-images.githubusercontent.com/113579489/191677536-1123754a-cbb2-4424-a754-d60608043571.png)

Відкрийте нові вкладки у Chrome, з якимись сайтами.

Відмітьте, що кількість потоків збільшилась.



![image](https://user-images.githubusercontent.com/113579489/191676810-987862a9-f72c-4969-8d20-35ccd7fff85f.png)

Виберіть кореневий процес chrome.exe і призупиніть його.
Для цього натискаємо правою кнопкою на процесі -> Suspend.

Результат буде такий, що ви не зможеше взаємодіяти з даним вікном, але
коли ви відновити процес все що ви робили буде відновленно

Тепер повертаємо назад всі його процеси
Для цього також натискаємо правою кнопкою на процесі -> Resume.

#  Потоки у Windows

У ProcessExplorer оберіть будь який процес. 
Відкрийте його властивості. Для цього правою кнопкою на процесі -> Properties.
Перейдіть на закладку Thereads.

![image](https://user-images.githubusercontent.com/113579489/191681234-a1ebc6ad-2417-426d-855c-2f4e2d342daa.png)

Зверніть увагу на кількість потоків.

![image](https://user-images.githubusercontent.com/113579489/191681496-326dc7b2-e38f-4a64-a7f5-8d789024eef6.png)

Для будь якого потоку відкрийте Stack.

![image](https://user-images.githubusercontent.com/113579489/191681596-914a29b1-e7c9-4017-9c27-0278cbaf39ce.png)

Запитання:
* Що знаходиться на найнижчому рівні? З якого dll починається стек?

Відповідь:
<p><b>dll</b> - динамічно приєднувана бібліотека. Як правило, бібліотеки мають розширення файлу *.dll, *.ocx (для бібліотек, що містять елементи керування ActiveX).
<p><b>ActiveX</b> - це невеликі програми, завдяки яким веб-сайти можуть відображати такий вміст, як відео та ігри. Під час перегляду веб-сторінок вони дають змогу взаємодіяти з таким вмістом, як панелі інструментів і фінансові символи.

* На найближчому рівні знаходить номер 9
*ntdll.dll!RtlUserThreadStart+0x21

# Дерево процесів Linux
Запустить віртуальну машину Ubuntu
<p>Відкрийте термінал 
<p>Виконайте команду 
```
pstree -p
```
```shell
systemd(1)─┬─ModemManager(479)─┬─{ModemManager}(512)
           │                   └─{ModemManager}(519)
           ├─NetworkManager(399)─┬─{NetworkManager}(480)
           │                     └─{NetworkManager}(481)
           ├─accounts-daemon(391)─┬─{accounts-daemon}(418)
           │                      └─{accounts-daemon}(448)
           ├─acpid(392)
           ├─anydesk(488)─┬─{anydesk}(523)
           │              ├─{anydesk}(524)
           │              └─{anydesk}(3073)
           ├─avahi-daemon(395)───avahi-daemon(447)
           ├─colord(1536)─┬─{colord}(1541)
           │              └─{colord}(1545)
           ├─containerd(492)─┬─{containerd}(525)
           │                 ├─{containerd}(526)
           │                 ├─{containerd}(527)
           │                 ├─{containerd}(528)
           │                 ├─{containerd}(537)
           │                 ├─{containerd}(538)
           │                 ├─{containerd}(539)
           │                 ├─{containerd}(1705)
           │                 └─{containerd}(1706)
           ├─containerd-shim(1729)─┬─uvicorn(1794)
           │                       ├─{containerd-shim}(1733)
           │                       ├─{containerd-shim}(1734)
           │                       ├─{containerd-shim}(1735)
           │                       ├─{containerd-shim}(1743)
           │                       ├─{containerd-shim}(1744)
           │                       ├─{containerd-shim}(1745)
           │                       ├─{containerd-shim}(1746)
           │                       ├─{containerd-shim}(1753)
           │                       ├─{containerd-shim}(1908)
           │                       ├─{containerd-shim}(1977)
           │                       └─{containerd-shim}(1988)
           ├─containerd-shim(1730)─┬─redis-server(1787)─┬─{redis-server}(1943)
           │                       │                    ├─{redis-server}(1944)
           │                       │                    ├─{redis-server}(1945)
           │                       │                    └─{redis-server}(1946)
           │                       ├─{containerd-shim}(1736)
           │                       ├─{containerd-shim}(1737)
           │                       ├─{containerd-shim}(1738)
           │                       ├─{containerd-shim}(1747)
           │                       ├─{containerd-shim}(1748)
           │                       ├─{containerd-shim}(1749)
           │                       ├─{containerd-shim}(1751)
           │                       ├─{containerd-shim}(1752)
           │                       ├─{containerd-shim}(1918)
           │                       ├─{containerd-shim}(1978)
           │                       └─{containerd-shim}(4182)
           ├─containerd-shim(1731)─┬─python3(1803)───{python3}(1960)
           │                       ├─{containerd-shim}(1740)
           │                       ├─{containerd-shim}(1741)
           │                       ├─{containerd-shim}(1742)
           │                       ├─{containerd-shim}(1750)
           │                       ├─{containerd-shim}(1754)
           │                       ├─{containerd-shim}(1755)
           │                       ├─{containerd-shim}(1756)
           │                       ├─{containerd-shim}(1757)
           │                       ├─{containerd-shim}(1926)
           │                       ├─{containerd-shim}(1979)
           │                       └─{containerd-shim}(4918)
           ├─cron(396)
           ├─cups-browsed(449)─┬─{cups-browsed}(498)
           │                   └─{cups-browsed}(499)
           ├─cupsd(397)
           ├─dbus-daemon(398)
           ├─dockerd(1288)─┬─docker-proxy(1688)─┬─{docker-proxy}(1690)
           │               │                    ├─{docker-proxy}(1691)
           │               │                    ├─{docker-proxy}(1692)
           │               │                    ├─{docker-proxy}(1693)
           │               │                    ├─{docker-proxy}(1695)
           │               │                    ├─{docker-proxy}(1696)
           │               │                    └─{docker-proxy}(1697)
           │               ├─docker-proxy(1694)─┬─{docker-proxy}(1698)
           │               │                    ├─{docker-proxy}(1699)
           │               │                    ├─{docker-proxy}(1700)
           │               │                    ├─{docker-proxy}(1701)
           │               │                    ├─{docker-proxy}(1702)
           │               │                    └─{docker-proxy}(1703)
           │               ├─{dockerd}(1319)
           │               ├─{dockerd}(1322)
           │               ├─{dockerd}(1323)
           │               ├─{dockerd}(1324)
           │               ├─{dockerd}(1325)
           │               ├─{dockerd}(1396)
           │               ├─{dockerd}(1409)
           │               ├─{dockerd}(1410)
           │               ├─{dockerd}(1689)
           │               ├─{dockerd}(1707)
           │               ├─{dockerd}(1709)
           │               ├─{dockerd}(1710)
           │               ├─{dockerd}(1839)
           │               └─{dockerd}(1842)
           ├─fwupd(3347)─┬─{fwupd}(3354)
           │             ├─{fwupd}(3374)
           │             ├─{fwupd}(3375)
           │             └─{fwupd}(3408)
           ├─gdm3(809)─┬─gdm-session-wor(2552)─┬─gdm-x-session(2642)─┬─Xorg(264+
           │           │                       │                     ├─gnome-se+
           │           │                       │                     ├─{gdm-x-s+
           │           │                       │                     └─{gdm-x-s+
           │           │                       ├─{gdm-session-wor}(2553)
           │           │                       └─{gdm-session-wor}(2554)
           │           ├─{gdm3}(813)
           │           └─{gdm3}(814)
           ├─gnome-keyring-d(2583)─┬─{gnome-keyring-d}(2584)
           │                       ├─{gnome-keyring-d}(2585)
           │                       └─{gnome-keyring-d}(2776)
           ├─irqbalance(405)───{irqbalance}(446)
           ├─kerneloops(1293)
           ├─kerneloops(1302)
           ├─networkd-dispat(427)
           ├─polkitd(429)─┬─{polkitd}(450)
           │              └─{polkitd}(452)
           ├─rsyslogd(432)─┬─{rsyslogd}(469)
           │               ├─{rsyslogd}(470)
           │               └─{rsyslogd}(471)
           ├─rtkit-daemon(966)─┬─{rtkit-daemon}(976)
           │                   └─{rtkit-daemon}(977)
           ├─snapd(433)─┬─{snapd}(600)
           │            ├─{snapd}(601)
           │            ├─{snapd}(602)
           │            ├─{snapd}(603)
           │            ├─{snapd}(604)
           │            ├─{snapd}(762)
           │            ├─{snapd}(764)
           │            ├─{snapd}(765)
           │            ├─{snapd}(769)
           │            ├─{snapd}(996)
           │            └─{snapd}(1108)
           ├─switcheroo-cont(435)─┬─{switcheroo-cont}(501)
           │                      └─{switcheroo-cont}(511)
           ├─systemd(2567)─┬─(sd-pam)(2568)
           │               ├─Keybase(3298)─┬─Keybase(3307)───Keybase(3350)─┬─{K+
           │               │               │                               ├─{K+
           │               │               │                               ├─{K+
           │               │               │                               ├─{K+
           │               │               │                               ├─{K+
           │               │               │                               └─{K+
           │               │               ├─Keybase(3308)───Keybase(3310)
           │               │               ├─Keybase(3356)─┬─{Keybase}(3358)
           │               │               │               ├─{Keybase}(3359)
           │               │               │               ├─{Keybase}(3360)
           │               │               │               └─{Keybase}(3364)
           │               │               ├─Keybase(3368)─┬─{Keybase}(3377)
           │               │               │               ├─{Keybase}(3379)
           │               │               │               ├─{Keybase}(3380)
           │               │               │               ├─{Keybase}(3381)
           │               │               │               ├─{Keybase}(3384)
           │               │               │               ├─{Keybase}(3385)
           │               │               │               ├─{Keybase}(3386)
           │               │               │               ├─{Keybase}(3387)
           │               │               │               └─{Keybase}(3411)
           │               │               ├─Keybase(3376)─┬─{Keybase}(3390)
           │               │               │               ├─{Keybase}(3392)
           │               │               │               ├─{Keybase}(3394)
           │               │               │               ├─{Keybase}(3395)
           │               │               │               ├─{Keybase}(3401)
           │               │               │               ├─{Keybase}(3402)
           │               │               │               ├─{Keybase}(3403)
           │               │               │               ├─{Keybase}(3404)
           │               │               │               └─{Keybase}(3410)
           │               │               ├─{Keybase}(3305)
           │               │               ├─{Keybase}(3311)
           │               │               ├─{Keybase}(3312)
           │               │               ├─{Keybase}(3313)
           │               │               ├─{Keybase}(3316)
           │               │               ├─{Keybase}(3317)
           │               │               ├─{Keybase}(3320)
           │               │               ├─{Keybase}(3321)
           │               │               ├─{Keybase}(3322)
           │               │               ├─{Keybase}(3323)
           │               │               ├─{Keybase}(3329)
           │               │               ├─{Keybase}(3337)
           │               │               ├─{Keybase}(3338)
           │               │               ├─{Keybase}(3339)
           │               │               ├─{Keybase}(3340)
           │               │               ├─{Keybase}(3341)
           │               │               ├─{Keybase}(3343)
           │               │               ├─{Keybase}(3346)
           │               │               ├─{Keybase}(3348)
           │               │               ├─{Keybase}(3349)
           │               │               ├─{Keybase}(3351)
           │               │               ├─{Keybase}(3352)
           │               │               ├─{Keybase}(3357)
           │               │               └─{Keybase}(3367)
           │               ├─at-spi-bus-laun(2760)─┬─dbus-daemon(2765)
           │               │                       ├─{at-spi-bus-laun}(2761)
           │               │                       ├─{at-spi-bus-laun}(2762)
           │               │                       └─{at-spi-bus-laun}(2764)
           │               ├─at-spi2-registr(2840)─┬─{at-spi2-registr}(2841)
           │               │                       └─{at-spi2-registr}(2842)
           │               ├─chrome(4227)─┬─cat(4232)
           │               │              ├─cat(4233)
           │               │              ├─chrome(4244)───chrome(4278)─┬─{chro+
           │               │              │                             ├─{chro+
           │               │              │                             ├─{chro+
           │               │              │                             ├─{chro+
           │               │              │                             ├─{chro+
           │               │              │                             ├─{chro+
           │               │              │                             ├─{chro+
           │               │              │                             └─{chro+
           │               │              ├─chrome(4246)─┬─chrome(4253)─┬─chrom+
           │               │              │              │              ├─chrom+
           │               │              │              │              ├─chrom+
           │               │              │              │              ├─chrom+
           │               │              │              │              ├─chrom+
           │               │              │              │              ├─chrom+
           │               │              │              │              ├─chrom+
           │               │              │              │              ├─chrom+
           │               │              │              │              ├─chrom+
           │               │              │              │              ├─chrom+
           │               │              │              │              ├─chrom+
           │               │              │              │              ├─chrom+
           │               │              │              │              ├─chrom+
           │               │              │              │              └─chrom+
           │               │              │              └─nacl_helper(4248)
           │               │              ├─chrome(4279)─┬─{chrome}(4281)
           │               │              │              ├─{chrome}(4282)
           │               │              │              ├─{chrome}(4284)
           │               │              │              ├─{chrome}(4298)
           │               │              │              ├─{chrome}(4909)
           │               │              │              ├─{chrome}(4919)
           │               │              │              ├─{chrome}(5043)
           │               │              │              ├─{chrome}(5045)
           │               │              │              └─{chrome}(5069)
           │               │              ├─chrome(4615)─┬─{chrome}(4629)
           │               │              │              ├─{chrome}(4631)
           │               │              │              ├─{chrome}(4632)
           │               │              │              ├─{chrome}(4633)
           │               │              │              └─{chrome}(4641)
           │               │              ├─{chrome}(4242)
           │               │              ├─{chrome}(4254)
           │               │              ├─{chrome}(4255)
           │               │              ├─{chrome}(4256)
           │               │              ├─{chrome}(4260)
           │               │              ├─{chrome}(4261)
           │               │              ├─{chrome}(4262)
           │               │              ├─{chrome}(4263)
           │               │              ├─{chrome}(4264)
           │               │              ├─{chrome}(4267)
           │               │              ├─{chrome}(4268)
           │               │              ├─{chrome}(4269)
           │               │              ├─{chrome}(4270)
           │               │              ├─{chrome}(4275)
           │               │              ├─{chrome}(4276)
           │               │              ├─{chrome}(4277)
           │               │              ├─{chrome}(4307)
           │               │              ├─{chrome}(4334)
           │               │              ├─{chrome}(4352)
           │               │              ├─{chrome}(4731)
           │               │              ├─{chrome}(4733)
           │               │              ├─{chrome}(4734)
           │               │              ├─{chrome}(4965)
           │               │              ├─{chrome}(5058)
           │               │              ├─{chrome}(5062)
           │               │              ├─{chrome}(5063)
           │               │              ├─{chrome}(5064)
           │               │              ├─{chrome}(5065)
           │               │              └─{chrome}(5066)
           │               ├─chrome_crashpad(4235)─┬─{chrome_crashpad}(4240)
           │               │                       └─{chrome_crashpad}(4241)
           │               ├─chrome_crashpad(4238)───{chrome_crashpad}(4239)
           │               ├─dbus-daemon(2578)
           │               ├─dconf-service(2872)─┬─{dconf-service}(2873)
           │               │                     └─{dconf-service}(2874)
           │               ├─evolution-addre(2881)─┬─{evolution-addre}(2884)
           │               │                       ├─{evolution-addre}(2885)
           │               │                       ├─{evolution-addre}(2887)
           │               │                       ├─{evolution-addre}(2888)
           │               │                       └─{evolution-addre}(2890)
           │               ├─evolution-calen(2864)─┬─{evolution-calen}(2865)
           │               │                       ├─{evolution-calen}(2866)
           │               │                       ├─{evolution-calen}(2875)
           │               │                       ├─{evolution-calen}(2876)
           │               │                       ├─{evolution-calen}(2877)
           │               │                       ├─{evolution-calen}(2879)
           │               │                       ├─{evolution-calen}(2880)
           │               │                       └─{evolution-calen}(2883)
           │               ├─evolution-sourc(2855)─┬─{evolution-sourc}(2858)
           │               │                       ├─{evolution-sourc}(2859)
           │               │                       └─{evolution-sourc}(2860)
           │               ├─gjs(2902)─┬─{gjs}(2910)
           │               │           ├─{gjs}(2911)
           │               │           ├─{gjs}(2914)
           │               │           └─{gjs}(2915)
           │               ├─gnome-session-b(2779)─┬─anydesk(2996)─┬─{anydesk}(+
           │               │                       │               ├─{anydesk}(+
           │               │                       │               ├─{anydesk}(+
           │               │                       │               ├─{anydesk}(+
           │               │                       │               ├─{anydesk}(+
           │               │                       │               ├─{anydesk}(+
           │               │                       │               └─{anydesk}(+
           │               │                       ├─evolution-alarm(2995)─┬─{e+
           │               │                       │                       ├─{e+
           │               │                       │                       ├─{e+
           │               │                       │                       ├─{e+
           │               │                       │                       └─{e+
           │               │                       ├─gsd-disk-utilit(2969)─┬─{g+
           │               │                       │                       └─{g+
           │               │                       ├─update-notifier(4648)─┬─{u+
           │               │                       │                       ├─{u+
           │               │                       │                       └─{u+
           │               │                       ├─{gnome-session-b}(2780)
           │               │                       ├─{gnome-session-b}(2781)
           │               │                       └─{gnome-session-b}(2783)
           │               ├─gnome-session-c(2772)───{gnome-session-c}(2778)
           │               ├─gnome-shell(2795)─┬─ibus-daemon(2819)─┬─ibus-engin+
           │               │                   │                   ├─ibus-exten+
           │               │                   │                   ├─ibus-memco+
           │               │                   │                   ├─{ibus-daem+
           │               │                   │                   └─{ibus-daem+
           │               │                   ├─{gnome-shell}(2806)
           │               │                   ├─{gnome-shell}(2808)
           │               │                   ├─{gnome-shell}(2809)
           │               │                   ├─{gnome-shell}(2811)
           │               │                   ├─{gnome-shell}(2812)
           │               │                   ├─{gnome-shell}(2813)
           │               │                   └─{gnome-shell}(5100)
           │               ├─gnome-shell-cal(2847)─┬─{gnome-shell-cal}(2850)
           │               │                       ├─{gnome-shell-cal}(2852)
           │               │                       ├─{gnome-shell-cal}(2853)
           │               │                       ├─{gnome-shell-cal}(2854)
           │               │                       └─{gnome-shell-cal}(2863)
           │               ├─gnome-terminal-(5091)─┬─bash(5099)───pstree(5109)
           │               │                       ├─{gnome-terminal-}(5092)
           │               │                       ├─{gnome-terminal-}(5093)
           │               │                       ├─{gnome-terminal-}(5094)
           │               │                       ├─{gnome-terminal-}(5097)
           │               │                       └─{gnome-terminal-}(5098)
           │               ├─goa-daemon(2627)─┬─{goa-daemon}(2628)
           │               │                  ├─{goa-daemon}(2630)
           │               │                  └─{goa-daemon}(2631)
           │               ├─goa-identity-se(2634)─┬─{goa-identity-se}(2635)
           │               │                       └─{goa-identity-se}(2637)
           │               ├─gsd-a11y-settin(2922)─┬─{gsd-a11y-settin}(2933)
           │               │                       ├─{gsd-a11y-settin}(2938)
           │               │                       └─{gsd-a11y-settin}(2942)
           │               ├─gsd-color(2923)─┬─{gsd-color}(2977)
           │               │                 ├─{gsd-color}(2978)
           │               │                 └─{gsd-color}(2993)
           │               ├─gsd-datetime(2924)─┬─{gsd-datetime}(2970)
           │               │                    ├─{gsd-datetime}(2985)
           │               │                    └─{gsd-datetime}(3022)
           │               ├─gsd-housekeepin(2925)─┬─{gsd-housekeepin}(2930)
           │               │                       ├─{gsd-housekeepin}(2940)
           │               │                       └─{gsd-housekeepin}(2945)
           │               ├─gsd-keyboard(2926)─┬─{gsd-keyboard}(2973)
           │               │                    ├─{gsd-keyboard}(2974)
           │               │                    └─{gsd-keyboard}(2990)
           │               ├─gsd-media-keys(2928)─┬─{gsd-media-keys}(2983)
           │               │                      ├─{gsd-media-keys}(2991)
           │               │                      ├─{gsd-media-keys}(3057)
           │               │                      └─{gsd-media-keys}(5086)
           │               ├─gsd-power(2932)─┬─{gsd-power}(3002)
           │               │                 ├─{gsd-power}(3039)
           │               │                 └─{gsd-power}(3062)
           │               ├─gsd-print-notif(2934)─┬─{gsd-print-notif}(2946)
           │               │                       └─{gsd-print-notif}(2955)
           │               ├─gsd-printer(3035)─┬─{gsd-printer}(3061)
           │               │                   └─{gsd-printer}(3072)
           │               ├─gsd-rfkill(2936)─┬─{gsd-rfkill}(2947)
           │               │                  └─{gsd-rfkill}(2952)
           │               ├─gsd-screensaver(2939)─┬─{gsd-screensaver}(2949)
           │               │                       └─{gsd-screensaver}(2953)
           │               ├─gsd-sharing(2941)─┬─{gsd-sharing}(2959)
           │               │                   ├─{gsd-sharing}(2960)
           │               │                   └─{gsd-sharing}(2971)
           │               ├─gsd-smartcard(2944)─┬─{gsd-smartcard}(2963)
           │               │                     ├─{gsd-smartcard}(2968)
           │               │                     ├─{gsd-smartcard}(3012)
           │               │                     └─{gsd-smartcard}(3013)
           │               ├─gsd-sound(2948)─┬─{gsd-sound}(2961)
           │               │                 ├─{gsd-sound}(2967)
           │               │                 └─{gsd-sound}(3011)
           │               ├─gsd-usb-protect(2951)─┬─{gsd-usb-protect}(2962)
           │               │                       ├─{gsd-usb-protect}(2966)
           │               │                       └─{gsd-usb-protect}(3009)
           │               ├─gsd-wacom(2954)─┬─{gsd-wacom}(3033)
           │               │                 └─{gsd-wacom}(3044)
           │               ├─gsd-wwan(2956)─┬─{gsd-wwan}(2965)
           │               │                ├─{gsd-wwan}(2972)
           │               │                └─{gsd-wwan}(3021)
           │               ├─gsd-xsettings(2958)─┬─{gsd-xsettings}(3036)
           │               │                     ├─{gsd-xsettings}(3040)
           │               │                     └─{gsd-xsettings}(3054)
           │               ├─gvfs-afc-volume(2649)─┬─{gvfs-afc-volume}(2650)
           │               │                       ├─{gvfs-afc-volume}(2651)
           │               │                       └─{gvfs-afc-volume}(2653)
           │               ├─gvfs-goa-volume(2623)─┬─{gvfs-goa-volume}(2624)
           │               │                       └─{gvfs-goa-volume}(2625)
           │               ├─gvfs-gphoto2-vo(2645)─┬─{gvfs-gphoto2-vo}(2646)
           │               │                       └─{gvfs-gphoto2-vo}(2648)
           │               ├─gvfs-mtp-volume(2619)─┬─{gvfs-mtp-volume}(2620)
           │               │                       └─{gvfs-mtp-volume}(2622)
           │               ├─gvfs-udisks2-vo(2611)─┬─{gvfs-udisks2-vo}(2613)
           │               │                       ├─{gvfs-udisks2-vo}(2614)
           │               │                       └─{gvfs-udisks2-vo}(2616)
           │               ├─gvfsd(2598)─┬─gvfsd-trash(2905)─┬─{gvfsd-trash}(29+
           │               │             │                   └─{gvfsd-trash}(29+
           │               │             ├─{gvfsd}(2599)
           │               │             └─{gvfsd}(2600)
           │               ├─gvfsd-fuse(2603)─┬─{gvfsd-fuse}(2606)
           │               │                  ├─{gvfsd-fuse}(2607)
           │               │                  ├─{gvfsd-fuse}(2608)
           │               │                  ├─{gvfsd-fuse}(2609)
           │               │                  └─{gvfsd-fuse}(2610)
           │               ├─gvfsd-metadata(4643)─┬─{gvfsd-metadata}(4644)
           │               │                      └─{gvfsd-metadata}(4645)
           │               ├─ibus-portal(2831)─┬─{ibus-portal}(2832)
           │               │                   └─{ibus-portal}(2834)
           │               ├─ibus-x11(2828)─┬─{ibus-x11}(2837)
           │               │                └─{ibus-x11}(2838)
           │               ├─kbfsfuse(3262)─┬─{kbfsfuse}(3281)
           │               │                ├─{kbfsfuse}(3282)
           │               │                ├─{kbfsfuse}(3283)
           │               │                ├─{kbfsfuse}(3284)
           │               │                ├─{kbfsfuse}(3285)
           │               │                ├─{kbfsfuse}(3286)
           │               │                ├─{kbfsfuse}(3287)
           │               │                ├─{kbfsfuse}(3288)
           │               │                ├─{kbfsfuse}(3289)
           │               │                ├─{kbfsfuse}(3296)
           │               │                └─{kbfsfuse}(3297)
           │               ├─keybase(3200)─┬─{keybase}(3201)
           │               │               ├─{keybase}(3202)
           │               │               ├─{keybase}(3203)
           │               │               ├─{keybase}(3208)
           │               │               ├─{keybase}(3209)
           │               │               ├─{keybase}(3210)
           │               │               ├─{keybase}(3211)
           │               │               ├─{keybase}(3212)
           │               │               ├─{keybase}(3213)
           │               │               ├─{keybase}(3228)
           │               │               └─{keybase}(3229)
           │               ├─keybase-redirec(3261)─┬─{keybase-redirec}(3266)
           │               │                       ├─{keybase-redirec}(3267)
           │               │                       ├─{keybase-redirec}(3268)
           │               │                       ├─{keybase-redirec}(3269)
           │               │                       ├─{keybase-redirec}(3270)
           │               │                       ├─{keybase-redirec}(3272)
           │               │                       ├─{keybase-redirec}(3273)
           │               │                       ├─{keybase-redirec}(3274)
           │               │                       └─{keybase-redirec}(3275)
           │               ├─pulseaudio(2573)─┬─{pulseaudio}(2615)
           │               │                  ├─{pulseaudio}(2655)
           │               │                  └─{pulseaudio}(2656)
           │               ├─snap-store(3069)─┬─{snap-store}(3302)
           │               │                  ├─{snap-store}(3303)
           │               │                  ├─{snap-store}(3304)
           │               │                  └─{snap-store}(3336)
           │               ├─tracker-miner-f(2575)─┬─{tracker-miner-f}(2577)
           │               │                       ├─{tracker-miner-f}(2579)
           │               │                       ├─{tracker-miner-f}(2586)
           │               │                       └─{tracker-miner-f}(2654)
           │               ├─xdg-desktop-por(3318)─┬─{xdg-desktop-por}(3319)
           │               │                       ├─{xdg-desktop-por}(3324)
           │               │                       ├─{xdg-desktop-por}(3334)
           │               │                       ├─{xdg-desktop-por}(3335)
           │               │                       └─{xdg-desktop-por}(5103)
           │               ├─xdg-desktop-por(3326)─┬─{xdg-desktop-por}(3327)
           │               │                       ├─{xdg-desktop-por}(3328)
           │               │                       └─{xdg-desktop-por}(3333)
           │               ├─xdg-document-po(3103)─┬─{xdg-document-po}(3104)
           │               │                       ├─{xdg-document-po}(3110)
           │               │                       ├─{xdg-document-po}(3118)
           │               │                       ├─{xdg-document-po}(3120)
           │               │                       ├─{xdg-document-po}(3123)
           │               │                       └─{xdg-document-po}(5102)
           │               └─xdg-permission-(2844)─┬─{xdg-permission-}(2846)
           │                                       └─{xdg-permission-}(2849)
           ├─systemd-journal(250)
           ├─systemd-logind(436)
           ├─systemd-resolve(369)
           ├─systemd-timesyn(370)───{systemd-timesyn}(388)
           ├─systemd-udevd(283)
           ├─thermald(437)───{thermald}(717)
           ├─udisksd(438)─┬─{udisksd}(460)
           │              ├─{udisksd}(473)
           │              ├─{udisksd}(510)
           │              └─{udisksd}(560)
           ├─unattended-upgr(530)───{unattended-upgr}(556)
           ├─upowerd(1119)─┬─{upowerd}(1125)
           │               └─{upowerd}(1126)
           ├─whoopsie(1291)─┬─{whoopsie}(1304)
           │                └─{whoopsie}(1305)
           └─wpa_supplicant(441)

```
Пояснення:
<b>pstree</b> – команда, що показує процеси операціної системи у вигляді дерева, починаючи з процесу ініціалізації системи.
атрибут “p” включає у вивід ідентифікатор процесу PID.

<b>man</b> - це комадн для оримання документаці про дану команду
```  
man pstree
```
Запитання:
* Який ідентифікатор має кореневий процес системи?

Відповідь:
  systemd(1)─┬─ModemManager(479)─┬─{ModemManager}(512)


# Процеси Linux

Запустить віртуальну машину Ubuntu
<p>Відкрийте термінал 
<p>Виконайте команду 
```
  top
```

Пояснення за що відповідає даний вивід.
  [top](https://gadgetshelp.com/how-to/kak-ispolzovat-komandu-linux-top-dlia-pokaza-zapushchennykh-protsessov/)
  
Натисніть 
`f`
Відкриється можливіть обирати додаткові поля, оберіть додатково PPID та GROUP.
Для того аби вибрати використовуйте стрілочки вгору і вниз клавіатури.
Для вибору поля – пробіл.
Після вибору для виходу натисніть:
`q`

Запитання:
  Що означають атрибути PPID та GROUP?

