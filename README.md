

## Общие требования по результатам работы:

* Кроссбраузерность, кросплатформенность, 0 ошибок выполнения скриптов и подключения ресурсов - (10 последних версий браузеров OSX/iOS/Windows/Android).

* На данный момент необходимо делать десктоп и мобильную версию лендинга, без адаптивной верстки

* pixel-perfect верстка на макете (проверка через css регрессии)

* Весь код beautified – нормально структурирован.

* Изменения вносятся в оригинальные(не минифицированные) файлы

* При минификации css js файлов оригиналы остаются в папке проекта.

* Разработка ведется в пределах стандартной папки проекта с исползованием стандартного "упаковщика" проектов grunt.

* Разработка ведется с соблюдением всех регламентов и стандартов команды(!).

* Разработка приоритетно на стандартных плагинах, исходники которого лежат в стандартной папке проекта(они подверглис изменений).
* Разработка приоритетно с использовнием командных Gist'ов https://gist.github.com/play0for0fun

* Все страницы максимум оптимизированны на скорость загрузки с использованием стандартного "упаковщика" проектов grunt, и с соблюдением всех регламентов

* Все пути к ресурсам должны быть прописаны отноительно а не абсолютно

* При работе над страницей нужно соблюдать стандарт подключения ресурсов https://gist.github.com/play0for0fun/7c8ee3fe3cd03dd84db75a0ac940c333

* Каждая форма отправки данных должна быть идентифицированна и иметь свою цель ГА/ЯМ

* При неправельном заполнении формы должно появляться popup уведомление о необходимости ввести нужные данные

* Нельзя использовать плагины для реализации фулпейдж, только верстка и скриптовка по стандартам команды

* На главной странице десктоп версии должен быть установлен css прелоадер который отключается при инициализации

* Нельзя использовать библиотеку wow.js  animate.css

* Запрещенно использование фреймворка bootstrap и подобных для верстки сайтов

* На планшетах и мобильных устройствах должен отключатся фулпейдж и прелоадер

* Вместе с данными с формой должны приходить данные идентификации, все выбранные параметры и данные относящихся к этой форме, стандартные ютм метки и геоданные

* Библиотеки webfont и jquery должны подключатся с CDN



## Стандар папки проекта:

* src/ - папка исходников

* dist/ - папка "упакованного" проекта

* src/desktop/ - папка исходников desktop версии

* src/tablet/ - папка исходников tablet версии

* src/mobile/ - папка исходников mobile версии

* src/track/ - файлы блоков для подключения счетчиков/пикселей/мультилендги

* src/track/head.php - блок который подключается перед /head

* src/track/body.php - блок который подключается перед /body

* src/desktop/.httaccess - файл серверных настроек apache 

* src/[version]/img/ - папка графических ресурсов 

* src/[version]/ajax/ - папка ресурсов которые загружаются отложенно либо с использованием технологии ajax

* src/[version]/ajax/mail.php - файл отправщик почты

* src/[version]/js/ - папка js ресурсов 

* src/[version]/js/libs/*.js -  js файлы использованных библиотек

* src/[version]/js/libs.js - js файл-склейка использованных библиотек

* src/[version]/js/init.js - js файл инциализации версии

* src/[version]/js/main.js - основной скрипт версии

* src/[version]/js/map.js - стандартный скрипт карты

* src/[version]/css/ - папка сss ресурсов 

* src/[version]/css/libs/*.css -  css файлы использованных библиотек

* src/[version]/css/sass/style.scss - scss файл основного стиля версии для препроцессора SASS

* src/[version]/css/libs.css - css файл-склейка использованных библиотек

* src/[version]/css/style.css - css файл оснвного стиля версии, может быть результатом компиляции SASS

* src/[version]/css/media.css - css файл стиля медиа-запросов (@media) версии

* src/[version]/css/scripts.css - css файл дополнительных стилей для работы скриптов

* src/[version]/css/head.css - css файл критического стиля, должен обязательно вмещать описание стиля фона первого блока и описание стиля для работы прелоадера


## Работа с стандартным "упаковщиком" grunt:

* Файл настроек grunt - change_and_rename_Gruntfile.js. В верхней части расположены параметры файла. После настройки нужно прееименировать в Gruntfile.js

* Параметр mobile = false||true - используется или нет мобильная версия

* Параметр tablet = false||true - используется или нет планшетная версия

* Параметр adaptive = false||true - адаптиваня верстка или нет(если true, то mobile и tablet false)
  
* Параметр ft_target = 'src/desktop/'||'dist/' - целевая папка для загрузки

* Параметр ft_folder = 'black.swan/www/standarts/' - папка на хостинге куда загружать

* Параметр ft_host = 'ftp.black.swan' - адрес сервера подключения

* Файл с логином/паролем к хостингу - rename_.ftppass. После изменения нужно переименировать в .ftppass (этот файл не синхронизируется, внесен в gitignore)

* Команды для установки всех нужных плагинов grunt находятся в верхней части terminal_command.txt

* После установки, настройки и переименирования будут доступны следующие команды: grunt, grunt start, grunt check, grunt fin, grunt ftp

* grunt - включает функция слежения за файлами библиотек и исходниками препроцессоров. При изменении обновляет файлы libs.css, libs.js, компилирует sass

* grunt start - делает beautify всех исходников

* grunt check - проверяет валидность исходников, csshint, jslint

* grunt fin - упаковывает исходникик в dist/ с оптимизацией и проверкой валидатором

* grunt ftp - совершает выгрузку целевой папки на хостинг



## Другие стандартные файлы репозитория:

* .csscomb.json - файл настроек для beautify css

* .gitignore - найтройка ингнорируемых файлов в пределах репозитория

* terminal_commands.txt - файл с консольными командами для установки grunt и инструмента тестирования css регрессиями

* rename_backstop.json - файл с настройками тестов верстки. После установки иснтрумента тестирования css регрессиями, нужно переименировать в backstop.json

* rename_backstop_data/ - папка для тестов верстки. После установки иснтрумента тестирования css регрессиями, нужно переименировать в backstop_data/


## Требования к написанию html кода:

* Верстка по стандартам html5 – 0 ошибок валидатора https://validator.w3.org/

* Верстка должна иметь карту заголовков без ошибок(https://validator.w3.org/ опция outline) 

* До и после br в одной строке, перед br всегда есть пробел, даже после оптимизации

* Табуляция 4 пробела/Tab

* Нету пустых строк и лишних пробелов

* Минимальное количество элементов html (исключить лишние вложения, чаще использовать :before и :after)

* Прописаны meta charset,viewport,favicon

* Допускается использовать блок style /style только(!) в head в целях оптимизации скорости загрузки, в этом случае содержимое находится в src/css/head.css и импортируются средствами php - style ? include('css/head.css'); ? /style

* Для привязки стилей приоритетно пользуемся классами и вложениями

* На этапе верстки рекомендуется использовать только 1н класс на елементе(!), исключения елементы имеющие несколько состояний(active,disactive), в этом случае допускается использование второго (.active,.disactive) класса

* html  код сайта семантичен. Тексты должны быть текстами (p, span), заголовки заголовками (h1-h6), формы формами (form), списки-списками, тдтп. Контентовые картинки (не фоновые) img

* Кнопки a или button

* table tr td использовать только(!) для разметки таблиц

* Только один h1

* html lang="ru"

* Запрещено использовать инлайн-стили (атрибут style="")

* Не использовать on[event] атрибуты(onclick,onsubmit,onchange)

* Все img имеют заполненные атрибуты width и height

* Допускается script[code]/script в /head для перернаправления между страницами-версиями/АБ вариантами

* Коды трекингов/плагинов/сервисов вынесены в отдельные файлы для /head и /body соответвенно

* Основные скрипты в оптимизированной версии подключаются асинхронно перед  /head а в источниках синхронно перед /body


## Требования к написанию css кода:

* Использовать библиотеку normalize.css

* Стили сайта (css) вынесены в отдельные файлы: libs.css(стили библиотек) style.css(стили статической верстки) media.css(медиазапросы) scripts.css(стили скриптов) head.css(часть css необходимая для отобржания(!) первого екрана)

* Учитывать разный рендер шрифтов в разных осях, браузерах, размерах экранов - фиксировать ширины текстовых блоков с запасом min 10px

* Aктивно использвоать наследование и каскадирование

* Использование препроцессоров css приветстсвуется

* Шрифты подключаются целыми семействами - {font-family:Open Sans;font-weight:300}, а не {font-family:opensanslight}.

* Плавность css анимаций (.button{transition:all 0.25s})

* Правильное использование margin и padding

* Правильное использование css position и только там где это необходимо.

* Правильные выборы форматов изображений (png/jpg) и их размеров. Не использвоать картинки для одноцветных фонов.

* Выполнение функций фотошопа таких как тень, прозрачность скругливание углов средствами css.

* Срезы картинок, функция линейного градиента фотошоп -  средствами css

* Обязательное описание :hover и :active состояний на активных элементах

* Использовать !important только там где это необходимо

* Написание новых css правил в соответсвующих файлах

* Кроссбраузерность, кросплатформенность (android 4.4.1+, iOS7+, desctop)

* Автопрефикс выходного css с параметрами ie >= 8,last 10 versions,> 0.1%

* Не вносить изменения в src/[version]/css/libs.css, src/[version]/css/style.css если они результат работы препроцессора

* При использовании position:absolute, position:relative, position:fixed в пределах правила должен стоять z-index (android 4.4.1 bug)

* Не использовать vh vw измерения, кроме как 100vh для создания фулл-пейдж блока(android 4.4.1 bug)

* Не использовать селекторы  :nth-child(), :first-child, last-child, на замену им - :nth-of-type() (iOS8 bug)

* Не использовать сокращенный(Универсальный) background, на замену ему background-color,background-image,background-repeat,background-position (android 4.4.1 bug)

* Не использовать transform:translateX(),transform:translateY(),transform:translateZ(), на замену им transform:translate3d() (android 4.4.1, iOS8 bug [NS](http://webdone.info/reporting/test/in.html))

* При использовании background-size:cover в пределах правила должен стоять position:absolute/position:relative (android 4.4.1 bug)

* Если в текстовом блоке использовано br фиксировать размер блока по высоте (android 4.4.1 bug изменение ширины текстовых блоков до ширины экрана)


## Требования к написанию jsкода:

* Использование jQuery

* Кроссбраузерность, кросплатформенность (android 4.4.1+, iOS7+, desctop)

* 0 ошибок выполнения

* Рекомендуемые решения https://gist.github.com/play0for0fun

* Не вносить изменения в src/[version]/js/libs.js, src/js/libs/*.js

* Основной скрипт сайта - src/[version]/js/main.js

* Каждая логическая часть откоментирована

* Правильное распределние функций между document.ready, window.load, $

* В оптимизированной версии все img загружаются по технологии lazyload

* Максимально быстрый рендер страницы(минимум необходимых функций для инициализации) 

* Используйте данные  в тегах html элементов (href,data-XXXX) для объединений аналогичных функций (например вызов попапов по клику, переход к слайду, тдтп)

* Минимум использования глобальных переменных

* Не использовать setInterval только рекурсивный вызов через setTimeout обязательно с условиям выхода из рекурсии

* Рекомендуемая библиотека для галерей - fancybox, для слайдеров - bxslider, для модальных окон - arcticmodal

* Тэги <? в файлах php должны быть прописаны как <?php

* загрузка iframe отложена (youtube,карта) - например включаются в код при вызове аснихронно $ .append() / $ .appendTo()

* загрузка audio, video отложена (youtube,карта) - например включаются в код при вызове аснихронно $ .append() / $ .appendTo()