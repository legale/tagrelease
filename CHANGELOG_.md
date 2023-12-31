# CHANGELOG
## v1.1.1-0 28-08-2023 BUGFIX RELEASE
### bugs:
- [c626d6c38c1eca355f2d1c026c366f7c1cf5d249] 14
  
## v1.1.0-0 28-08-2023 MINOR RELEASE
### bugs:
- [af653a5e96d1c12fbf363afadf89ad2c1fc5ffe3] [chore] Оптимизирован код обработки событий в контроллере для снижения нагрузки на процессор
  Выполнена оптимизация кода обработки событий в контроллере
WiFi точек доступа, что снизило нагрузку на
процессор и улучшило производительность системы.


- [b9d864b1717a81fd577607a3e2bec2fd366668d6] [fix] Исправлена ошибка, приводящая к периодическим сбоям  в работе контроллера точек доступа
  Проблема, вызывавшая периодические сбои в работе
контроллера точек доступа, была устранена,
обеспечивая стабильную и надежную работу системы.



### features:
- [3b015104267cfb62900487f507464ac678e65f87] [feat] Новая функция массовой активации WiFi точек доступа для упрощения масштабирования сети
  Внедрена инновационная функция массовой активации WiFi
точек доступа, позволяющая быстро масштабировать сеть
и упростить процесс настройки.


## v1.0.0-0 28-08-2023 MAJOR RELEASE
### bugs:
- [3c3009b9cbb5d79d9752085bbe37d9b66e799713] [docs] Обновлена документация по настройке и установке контроллера WiFi точек доступа
  Документация теперь содержит актуальные инструкции
по установке и настройке контроллера WiFi точек доступа,
облегчая процесс развертывания.


- [ab9ea52541c4234d3acdaef211cccf7c041d5f1a] [fix] Исправлена утечка памяти, возникающая при длительной работе контроллера в средах высокой загрузки
  Устранена проблема утечки памяти, которая могла возникнуть
при длительной эксплуатации контроллера в условиях
высокой загрузки сети.


- [fff5812e3739d1753cfd3789b748b4d898aded0d] [feat!] улучшение производительности в контроллере точек доступа
  Внедрено революционное улучшение производительности в
контроллере точек доступа, существенно повышающее скорость
и эффективность работы.


- [54ee94f40ed223a5df5bfd95151a034aaa8c2df4] [fix] неправильной обработкой паролей при настройке WiFi точек доступа
  Проблема с некорректной обработкой паролей при настройке WiFi точек доступа
была исправлена, что гарантирует безопасное подключение к сети.



### features:
- [a0bd06540b87c7e3ff5764b8b9e5715e7a66b0db] [feat] Внедрена поддержка WPA3 для повышения безопасности ваших WiFi сетей
  Добавлена поддержка протокола WPA3, усиливающего
безопасность WiFi сетей и обеспечивающего более
надежное шифрование данных.


- [24686ba6b5615969e76b032f5f227aea5e0e69c7] [feat] Добавлена возможность удаленного управления настройками QoS для WiFi точек доступа
  Введена новая функция, позволяющая удаленно управлять
настройками качества обслуживания (QoS) для WiFi точек
доступа, обеспечивая более гибкую настройку сетевых приоритетов.


## v0.1.0-0 27-08-2023 MINOR RELEASE
### bugs:
- [37796b3fb3dbea0aa44fc9821d4e96368371d770] We have to move to use git clone as there are no newer tagged releases.
  Changes:
604f8f5 Default CROSS_CM3 to arm-none-eabi- instead of armv7m-softfloat-eabi-
b9b9419 Tidy up license information
0290b2c wtmi: Fix typo
a10b8e9 Makefile: fix a53-firmware.bin generation (maximum size is not optimal)
f654082 wtmi: Add const qualifier to isr_vector
4a43a3b wtmi: Improve detection of ESPRESSObin boards with Topaz
189e629 wtmi: Improve detection of boards with insufficient MDIO pull-up
3dac4fe wtmi: Fix detection of Armada 3720 Devel Board
3ca4dfa Bump mox-imager commit

This is MD:
```
1. hello
1. my
    1. dear
1. friend
```


- [1297403b5d88c4f75cbde0c7928d297723dacfae] [fix]: bug wrong return in whateverfunc()
  

### features:
- [a7fdacff3ab55ddfbbb1c11b5b633fb8b40de696] [feat] Добавлена поддержка множественных SSID в контроллере WiFi точек доступа
  Теперь контроллер позволяет настроить несколько уникальных SSID на одной точке
доступа, обеспечивая гибкость в настройке сетей для различных пользователей.


- [410d2ab438292015687dbefd732ef79278b6009b] [feat]: initialized  to release 1.0.0
  
## v0.0.1-0 27-08-2023 BUGFIX RELEASE
### bugs:
- [f507f66bee51c0dc51c0b4ffccd97262a4e88420] [fix]: fix bug 2
  
- [9d2f269b0b4d7ca579d40e9ceb8900d6bd839602] 1
  
