/* место для вашего кода */ 

/* Плавная прокрутка страницы */ 

html { 

    scroll-behavior: smooth; 

} 

 

/* Шапка сайта */ 

header { 

    position: relative; 

    display: grid; 

    grid-template-columns: 1fr min-content 1fr; 

    align-items: center; 

 

    min-height: 290px; 
Не следует ограничивать высоту блока, внутри которого есть какое-то содержимое. Размер, количество элементов или количество текста внутри может измениться, контента может быть больше или меньше, чем в макете. То есть здесь не нужна ни фиксированная высота, ни минимальная, ни максимальная. Любой блок должен адаптироваться по высоте под свое содержимое.
Надо исправить
Антон Щепетков
ревьюер

 

    padding: 0 50px; 

    margin-bottom: 3px; 

} 

 

/* Меню в шапке */ 

.nav-menu { 

    display: flex; 

    align-items: center; 

    gap: 13px; 

 

    font-size: 18px; 

    line-height: 22px; 

    white-space: nowrap; 

} 

 

/* Пункт меню */ 

.nav-menu-item { 

    list-style: circle; 

 

    font-weight: 400; 

    font-size: 18px; 

    line-height: 100%; 

    text-underline-offset: 4px; 

    text-decoration-thickness: 1px; 

} 

 

/* Пункт меню с маркером */ 

.dot { 
Для буллета не стоит создавать отдельный класс и реализовывать его через псевдоэлемент. 
Буллет у элементов списка есть по-умолчанию в любом браузере.   Разметьте навигационные ссылки через список ul li - все рекомендации и имена классов описаны в брифе, придерживайтесь требований в задании
Надо исправить
Антон Щепетков
ревьюер

    display: inline-flex; 

    align-items: center; 

    gap: 13px; 

} 

 

/* Маркер пункта меню */ 

.dot::before { 

    content: ""; 

 

    width: 6px; 

    height: 6px; 

 

    border-radius: 50%; 

    border: 0.5px solid black; 

} 

 

/* Логотип */ 

.logo { 

    width: 148px; 

    height: 105px; 

} 

 

/* Контакты в шапке */ 

.header-adress { 

    justify-self: end; 

    align-items: flex-start; 

 

    width: 240px; 

 

    font-size: 18px; 

    line-height: 24px; 

} 

 

/* Блок контакта */ 

.adress-block { 

    display: block; 

 

    width: max-content; 

    max-width: 100%; 

 

    font-style: normal; 

    text-decoration: underline; 

    text-underline-offset: 3px; 

    text-decoration-thickness: 1px; 

} 

 

/* Отмена подчёркивания */ 

.no_inline { 

    text-decoration: none; 

} 

 

/* =============== Обложка ================= */ 

/* Обложка */ 

.cover { 

    position: relative; 

 

    min-height: 757px; 

 

    padding-top: 165px; 

 

    background-image: url("../images/cover.jpg"); 

    background-size: cover; 

    background-position: center; 

} 

 

/* Затемнение обложки */ 

.overlay { 

    position: absolute; 

    inset: 0; 

    z-index: 0; 

 

    background-color: rgba(0, 0, 0, 0.6); 

} 

 

/* Заголовок обложки */ 

.cover-title { 

    position: relative; 

    z-index: 1; 

    display: flex; 

    flex-direction: column; 

 

    margin-left: 50px; 

    margin-right: 50px; 

} 

 

/* Слово заголовка обложки */ 

.cover-text { 

    margin-right: -0.3em; 

 

    font-weight: 700; 

    font-size: 100px; 

    line-height: 115%; 

    letter-spacing: 0.3em; 

    text-transform: uppercase; 

 

    color: white; 

} 

 

/* Первое слово: слева */ 

.cover-text:nth-child(1) { 

    text-align: left; 

} 

 

/* Второе слово: по центру */ 

.cover-text:nth-child(2) { 

    margin-top: 20px; 

 

    text-align: center; 

} 

 

/* Третье слово: справа */ 

.cover-text:nth-child(3) { 
Не стоит привязывать стили к порядковому номеру элемента. Элементы могут меняться местами. Изменение порядка элементов не должно приводить к изменению их внешнего вида. Более корректным вариантом будет использование вспомогательных классов для каждого элемента. 
Например, менеджер по контенту может захотеть отобразить несколько строк, которые будут отцентрированы. При текущих стилях это реализовать было бы невозможно. Отцентрирована будет только вторая строка. 
Реализуйте центрирование через отдельные классы (в брифе перечислены рекомендуемые классы, которые вы можете использовать) 
Надо исправить
Антон Щепетков
ревьюер

    margin-top: 20px; 

 

    text-align: right; 

} 

 

/* Описание и кнопка на обложке */ 

.description { 

    position: relative; 

    z-index: 1; 

    display: flex; 

    align-items: center; 

    justify-content: space-between; 

 

    margin: 106px 50px auto 50px; 

} 

 

/* Текст описания */ 

.description-text { 

    font-size: 22px; 

    line-height: 28px; 

    letter-spacing: 0.2px; 

    word-spacing: 0.8em; 

    text-transform: uppercase; 

 

    color: white; 

} 

 

/* Кнопка «Сделать ставку» */ 

.description-button { 
Это элемент взаимодействия с пользователем. Ему хорошо бы добавить свойство cursor: pointer, чтобы при наведении курсор менялся, оповещая пользователя, что это интерактивный элемент и на него можно нажать
Можно лучше
Антон Щепетков
ревьюер

    width: 256px; 

    height: 51px; 
У кнопки не стоит жёстко ограничивать высоту, вместо этого лучше использовать более мягкое свойство для минимальной высоты -min-height, либо через внутренние отступы padding сверху и снизу. 
 В отличие от других мест, где высота в большинстве случаев вообще не нужна, у кнопки всегда будет какой-то текст. Кнопка без текста не будет иметь смысл, поэтому у неё всегда будет какая-то минимальная высота, которую удобно задать через min-height. В таком случае, более длинный текст сможет растягивать кнопку. Если зафиксировать высоту через height, то длинный текст будет выпадать из кнопки.
Можно лучше
Антон Щепетков
ревьюер

 

    font-weight: 400; 

    font-size: 22px; 

    line-height: 100%; 

    text-align: center; 

    text-transform: uppercase; 

 

    color: white; 

    background-color: transparent; 

 

    border: 1px solid white; 

} 

 

/* =============== Лоты ================= */ 

/* Секция «Лоты» */ 

.lots { 

    width: 1052px; 

    min-height: 723px; 
Не следует ограничивать высоту блока, внутри которого есть какое-то содержимое. Размер, количество элементов или количество текста внутри может измениться, контента может быть больше или меньше, чем в макете. То есть здесь не нужна ни фиксированная высота, ни минимальная, ни максимальная. Любой блок должен адаптироваться по высоте под свое содержимое.
Надо исправить
Антон Щепетков
ревьюер

 

    margin: 180px auto 0px; 

    padding-top: 5px; 

} 

 

/* Заголовок секции лотов */ 

.lots-title { 

    margin-left: 40px; 

 

    font-weight: 700; 

    font-size: 40px; 

    line-height: 100%; 

    text-transform: uppercase; 

} 

 

/* Список карточек лотов */ 

.card-list { 

    display: flex; 

    flex-wrap: wrap; 

    align-items: stretch; 

    gap: 25px; 

    list-style: none; 

 

    margin-top: 30px; 

    margin-bottom: 30px; 

} 

 

/* Элемент списка карточек */ 

.card-list-item { 

    flex: 1 1 300px; 

    max-width: 334px; 

    min-height: 596px; 
Не стоит задавать одинаковую минимальную высоту у двух вложеных друг в друга элементов. 
Минимальная высота должна быть задана только у дочернего элемента, а родительский автоматически подстроится под высоту дочернего блока.
Надо исправить
Антон Щепетков
ревьюер

} 

 

/* Ссылка на карточку */ 

.card-link { 

    display: block; 

 

    height: 100%; 

 

    text-decoration: none; 

 

    color: inherit; 

} 

 

/* Карточка лота */ 

.card { 

    position: relative; 

    isolation: isolate; 

    display: flex; 

    flex-direction: column; 

    justify-content: space-between; 

    overflow: hidden; 
Свойство overflow со значением hidden используется, чтобы целенаправленно обрезать какую-то часть на странице. Здесь обрезать ничего не нужно. Строку нужно удалить.
Надо исправить
Антон Щепетков
ревьюер

 

    height: 100%; 

    min-height: 596px; 

 

    padding: 48px 40px; 

 

    color: white; 

    background-size: cover; 

    background-position: center; 

} 

 

/* Карточка: фильм */ 

.card_type_film { 

    background-image: url("../images/card-lot-01.jpg"); 

} 

 

/* Карточка: книга */ 

.card_type_book { 

    background-image: url("../images/card-lot-02.jpg"); 

} 

 

/* Карточка: картина */ 

.card_type_picture { 

    background-image: url("../images/card-lot-03.jpg"); 

} 

 

/* Затемнение карточки */ 

.card .overlay { 

    z-index: 0; 

} 

 

/* Текст поверх карточки */ 

.card-title, 

.card-text { 

    position: relative; 

    z-index: 1; 

} 

 

/* Заголовок карточки */ 

.card-title { 

    margin: 0; 

 

    font-size: 22px; 

    font-weight: 700; 

    line-height: 1.2; 

    text-transform: uppercase; 

    text-decoration: underline; 

    text-decoration-thickness: 1px; 

    text-underline-offset: 1px; 

 

    color: white; 

} 

 

/* Описание в карточке */ 

.card-text { 

    margin: 0; 

 

    font-size: 20px; 

    font-weight: 400; 

    line-height: 1.2; 

 

    color: white; 

} 

 

/* Ссылка «посмотреть больше» */ 

.lots-more { 

    margin-left: 40px; 

 

    font-weight: 400; 

    font-size: 20px; 

    line-height: 100%; 

    text-decoration: underline; 

    text-decoration-thickness: 1px; 

    text-underline-offset: 5px; 

} 

 

/* =============== Об аукционе ================= */ 

/* Секция «Об аукционе» */ 

.about { 

    position: relative; 

 

    height: 595px; 
Не следует ограничивать высоту блока, внутри которого есть какое-то содержимое. Размер, количество элементов или количество текста внутри может измениться, контента может быть больше или меньше, чем в макете. То есть здесь не нужна ни фиксированная высота, ни минимальная, ни максимальная. Любой блок должен адаптироваться по высоте под свое содержимое.
Надо исправить
Антон Щепетков
ревьюер

 

    margin: 120px 24px 180px 24px; 

} 

 

/* Круглый логотип */ 

.logo-round { 

    position: absolute; 
Абсолютное позиционирование должно использоваться только там, где нельзя применить статичное или относительное позиционирование. Абсолютное позиционирование убирает блок из потока и страница уже не сможет реагировать на изменение количества контента в этом блоке. Единственное место в данной проектной работе, где подходит и допускается абсолютное позиционирование - это затемняющий слой (линза) во входной секции и в карточках. В остальных местах для разметки используйте флексы и гриды, не прибегая к использованию абсолютного позиционирования
Надо исправить
Антон Щепетков
ревьюер

    left: 47px; 

    top: 35px; 

    display: flex; 

    align-items: center; 

    justify-content: center; 

 

    width: 240px; 

    height: 240px; 

 

    background-color: black; 

 

    border-radius: 120px; 

} 

 

/* Изображение в круглом логотипе */ 

.logo-round img { 

    width: 148px; 

} 

 

/* Колонка секции «Об аукционе» */ 

.about_column { 

    position: absolute; 
Абсолютное позиционирование должно использоваться только там, где нельзя применить статичное или относительное позиционирование. Абсолютное позиционирование убирает блок из потока и страница уже не сможет реагировать на изменение количества контента в этом блоке. Единственное место в данной проектной работе, где подходит и допускается абсолютное позиционирование - это затемняющий слой (линза) во входной секции и в карточках. В остальных местах для разметки используйте флексы и гриды, не прибегая к использованию абсолютного позиционирования
Надо исправить
Антон Щепетков
ревьюер

    right: 0px; 

    bottom: 0px; 

    display: flex; 

    flex-direction: column; 

    align-items: start; 

    justify-content: space-between; 

 

    width: 693px; 

} 

 

/* Заголовок секции «Об аукционе» */ 

.about_column h2 { 

    margin-bottom: 100px; 

 

    font-weight: 700; 

    font-size: 40px; 

    line-height: 100%; 

    text-transform: uppercase; 

} 

 

/* Блок описания аукциона */ 

.description_block { 

    display: flex; 

    flex-direction: column; 

    align-items: center; 

    justify-content: space-between; 

    gap: 25px; 

} 

 

/* Абзац описания аукциона */ 

.description_block p { 

    font-weight: 400; 

    font-size: 20px; 

    line-height: 24px; 

} 

 

/* =============== Подвал ================= */ 

/* Подвал сайта */ 

footer { 

    position: relative; 

    display: grid; 

    grid-template-columns: 1fr 1fr 1fr; 

    align-items: start; 

 

    min-height: 180px; 
Не следует ограничивать высоту блока, внутри которого есть какое-то содержимое. Размер, количество элементов или количество текста внутри может измениться, контента может быть больше или меньше, чем в макете. То есть здесь не нужна ни фиксированная высота, ни минимальная, ни максимальная. Любой блок должен адаптироваться по высоте под свое содержимое.
Надо исправить
Антон Щепетков
ревьюер

 

    padding: 1px 50px; 

} 

 

/* Контакты в подвале */ 

.footer-adress { 

    justify-self: start; 

    align-items: flex-start; 

 

    width: 240px; 

 

    font-size: 18px; 

    line-height: 24px; 

} 

 

/* Меню в подвале */ 

.footer-menu { 

    display: flex; 

    flex-direction: column; 

    align-items: center; 

    gap: 3px; 

 

    margin-top: 2px; 

 

    font-size: 18px; 

    line-height: 22px; 

    white-space: nowrap; 

} 

 

/* Пункт меню подвала */ 

.footer-menu-item { 

    list-style: circle; 

 

    font-weight: 400; 

    font-size: 18px; 

    line-height: 100%; 

    text-underline-offset: 4px; 

    text-decoration-thickness: 1px; 

} 

 

/* Соцсети в подвале */ 

footer .socials { 

    justify-self: end; 

    display: flex; 

    gap: 48px; 

} 

 

/* Ссылка на соцсеть */ 

footer .socials a { 

    width: 48px; 

    height: 48px; 

} 

 
html
index.html
3
5
3

<!doctype html> 

<html lang="ru"> 

 

<head> 

    <meta charset="UTF-8" /> 

    <meta http-equiv="X-UA-Compatible" content="IE=edge" /> 

    <meta name="viewport" content="width=device-width, initial-scale=1.0" /> 

    <title>Оно тебе надо — аукцион вещей, в которые никто не верил</title> 

    <link rel="stylesheet" href="fonts/fonts.css" /> 

    <link rel="stylesheet" href="styles/global.css" /> 

    <link rel="stylesheet" href="styles/style.css" /> 

</head> 
Отлично. head правильно заполнен
Отлично
Антон Щепетков
ревьюер

 

<body> 

    <header> 

        <nav class="nav-menu"> 
Отлично. Для навигационного блока использован семантический тег <nav>
Отлично
Антон Щепетков
ревьюер

            <a href="#top" class="nav-menu-item no_inline"> 

                главная 

            </a> 

            <a href="#lots" class="nav-menu-item dot"> 

                посмотреть лоты 

            </a> 

            <a href="#about" class="nav-menu-item dot"> 

                об аукционе 

            </a> 

        </nav> 

        <a><img src="images/logo-black.svg" alt="Логотип оно тебе не надо" class="logo"></a> 
Отлично. Логотип обёрнут ссылкой, но без указания атрибута href. Таким образом, этот элемент является ссылкой, но без логики перехода
Отлично
Антон Щепетков
ревьюер

        <address class="header-adress"> 

            <a href="tel:+99995555555" class="adress-block"> 

                +9 999 555 5555 

            </a> 

            <a href="mailto:info@sobaka.ge" class="adress-block"> 

                info@sobaka.ge 

            </a> 

            <p class="adress-block no_inline"> 

                наб. Принсенграхт 263-265, Амстердам 

            </p> 

        </address> 

    </header> 

    <main> 
Отлично - основной контент обёрнут в тег main
Отлично
Антон Щепетков
ревьюер

        <section class="cover" id="top"> 

            <div class="overlay"></div> 

            <h1 class="cover-title"> 
Это основной заголовок страницы. Для него верно выбран тег первого уровня. Помните, что заголовок первого уровня может быть только один на странице.
Отлично
Антон Щепетков
ревьюер

                <span class="cover-text">оно</span> 

                <span class="cover-text">тебе</span> 

                <span class="cover-text">надо</span> 

            </h1> 

            <div class="description"> 

                <p class="description-text"> 

                    Аукцион вещей, в которые никто не верил 

                </p> 

                <button class="description-button"> 
У кнопки в проекте хорошо бы указывать атрибут type с нужным значением. Подробнее: http://htmlbook.ru/html/button/type. Если данный атрибут не указать, то будет использован тип по-умолчанию submit, однако данный тип нужен для кнопок, которые отправляют данные в формах <form>. То есть для кнопок, которые отправляют форму, атрибут можно не указывать, для всех остальных кнопок атрибут стоит указывать. Для обычных кнопок значение атрибута должно быть button
Можно лучше
Антон Щепетков
ревьюер

                    Сделать ставку 

                </button> 

            </div> 

        </section> 

        <section class="lots" id="lots"> 

            <h2 class="lots-title">лоты</h2> 

            <ul class="card-list"> 

                <li class="card-list-item"> 

                    <a href="#" class="card-link"> 

                        <article class="card card_type_film"> 

                            <div class="overlay"></div> 

                            <h3 class="card-title"> 

                                Фильм режиссёра, который бросил киношколу 

                            </h3> 

                            <p class="card-text"> 

                                Не просто бросил, а ушёл с первой лекции. Какой была бы ваша 

                                ставка, если бы вы не знали, что режиссёр — Пол Томас Андерсон? 

                            </p> 

                        </article> 

                    </a> 

                </li> 

                <li class="card-list-item"> 

                    <a href="#" class="card-link"> 

                        <article class="card card_type_book"> 

                            <div class="overlay"></div> 

                            <h3 class="card-title"> 

                                Книга, где описан один скучный день из жизни рекламного агента 

                            </h3> 

                            <p class="card-text"> 

                                Объёмом почти в тысячу страниц. Иногда без знаков препинания и с переходами на 

                                древнеанглийский. В ней одновременно рассказывается о 16 июня 1904 года и об истории 

                                литературы, начиная с античных времён. И это всё накладывается на эпическую поэму 

                                Гомера. Сколько бы вы поставили на «Улисса» Джеймса Джойса? 

                            </p> 

                        </article> 

                    </a> 

                </li> 

                <li class="card-list-item"> 

                    <a href="#" class="card-link"> 

                        <article class="card card_type_picture"> 

                            <div class="overlay"></div> 

                            <h3 class="card-title"> 

                                Картина, которую повторит даже 5-летний сын маминой подруги 

                            </h3> 

                            <p class="card-text"> 

                                Ну действительно, там линия, тут кружочек, а здесь и вовсе что-то похожее на 

                                инфузорию-туфельку. Никаких полей, лесов, котиков... Сколько бы вы на такое поставили, 

                                если бы не знали, что это — одна из революционных работ Кандинского? 

                            </p> 

                        </article> 

                    </a> 

                </li> 

            </ul> 

            <a href="#" class="lots-more">посмотреть больше</a> 

        </section> 

        <section class="about" id="about"> 

            <div class="logo-round"> 

                <img src="images/logo-white.svg" alt="logo"> 

            </div> 

            <div class="about_column"> 

                <h2>Об аукционе</h2> 

                <div class="description_block"> 

                    <p>Здесь вы не встретите очередное пафосное собрание невероятно дорогого антиквариата. Наши лоты 

                        вообще 

                        не должны были попасть ни на один аукцион. Потому что кому нужен дневник девочки-подростка или 

                        картина, которую может нарисовать даже ребёнок? Кому нужны все эти странные вещи, созданные 

                        любителями?</p> 

                    <p>Слишком сложные или, наоборот, слишком простые. Опережающие своё время. В пух и прах растерзанные 
https://disk.yandex.ru/i/glupBeOsUWTdYQ
Тексты могут меняться. При добавлении или удалении параграфов расположения элементов должны оставаться как в макете 
Надо исправить
Антон Щепетков
ревьюер

                        критиками. Непринятые и непонятые. Когда-то они казались просто неудачными. Но, несмотря 

                        на критику, кажущуюся простоту или сложность, сейчас без этих лотов невозможно представить 

                        современную культуру. Когда в эти вещи не верил никто, продолжали верить их создатели. И сейчас 

                        эти 

                        лоты стали культовыми. </p> 

                </div> 

            </div> 

        </section> 

    </main> 

    <footer> 

        <address class="footer-adress"> 
Блоки с контактной информацией в хедере и футере выглядят одинаково, а значит имеют общую стилизацию. Стили таких блоков необходимо переиспользовать. Для этого создайте в CSS какой-то общий класс, например, .address и пропишите для него общие стили, которые есть у блока с контактной информацией в хедере и футере. А вспомогательные классы используйте для стилей, которые отличаются от общих или чтобы контролировать расположение или геометрию элементов в каком-то конкретном блоке.
Надо исправить
Антон Щепетков
ревьюер

            <a href="tel:+99995555555" class="adress-block"> 

                +9 999 555 5555 

            </a> 

            <a href="mailto:info@sobaka.ge" class="adress-block"> 

                info@sobaka.ge 

            </a> 

            <p class="adress-block no_inline"> 

                наб. Принсенграхт 263-265, Амстердам 

            </p> 

        </address> 

        <nav class="footer-menu"> 

            <a href="#top" class="footer-menu-item no_inline"> 
Про класс no_inline  - классы должны быть подходящими и не должны быть привязаны к визуальной составляющей. 
По макету одна из ссылок должна быть активной, то есть должна обозначать открытую на данный момент страницу. Сейчас у активной ссылки отсутствует подчёркивание, но дизайнеры могут поправить вид активной ссылки и сделать её, например, другого цвета, тогда класс no_inline уже не подойдёт, придётся менять и стили, и сам класс (а на реальном сайте страниц с таким классом может быть много). 
Класс должен передавать смысл, но не внешний вид. Обозначьте активную ссылку, например, классом link_active  - такой класс будет обозначать активную ссылку, при этом вид у неё может быть совершенно любым, при изменении внешнего вида у ссылки нам нужно будет просто поправить стили, а класс останется без изменения.
Надо исправить
Антон Щепетков
ревьюер

                главная 

            </a> 

            <a href="#lots" class="footer-menu-item"> 

                посмотреть лоты 

            </a> 

            <a href="#about" class="footer-menu-item"> 

                об аукционе 

            </a> 

        </nav> 

        <div class="socials"> 
Для улучшения семантики для повторяющихся сущностей можно использовать списки ul li
Можно лучше
Антон Щепетков
ревьюер

            <a href="https://www.youtube.com/watch?v=dQw4w9WgXcQ" aria-label="YouTube"> 
Ссылкам на внешние сайты можно добавить атрибут target="_blank", чтобы они открывались в новой вкладке.
 После того как пользователь прочитает интересующую его информацию на внешнем сайте ему будет легко вернуться на ваш сайт - нужно будет просто закрыть вкладку с внешним сайтом.
Можно лучше
Антон Щепетков
ревьюер

                <img src="images/yt.svg" alt="YT logo"> 

            </a> 

            <a href="https://vk.ru/index.php" aria-label="VK"> 

                <img src="images/vk.svg" alt="VK logo"> 

            </a> 

            <a href="https://ru.pinterest.com/" aria-label="Pinterest"> 

                <img src="images/pinterest.svg" alt="pinterest logo"> 

            </a> 

        </div> 

    </footer> 

 

</body> 

 

</html> 



# styles/style.css — добавлено 12 комментариев ревьюера
1. header → min-height: 290px — замечание о недопустимости фиксированной высоты у блока с содержимым (Надо исправить)
2. .dot — замечание о буллете: не нужен отдельный класс с псевдоэлементом, нужно использовать ul li (Надо исправить)
3. .cover-text:nth-child(3) — замечание о привязке стилей к порядковому номеру элемента, рекомендация использовать вспомогательные классы (Надо исправить)
4. .description-button — рекомендация добавить cursor: pointer (Можно лучше)
5. .description-button → height: 51px — рекомендация использовать min-height или padding вместо жёсткой высоты (Можно лучше)
6. .lots → min-height: 723px — замечание о высоте блока с содержимым (Надо исправить)
7. .card-list-item → min-height: 596px — замечание о дублировании минимальной высоты у вложенных элементов (Надо исправить)
8. .card → overflow: hidden — замечание о лишнем свойстве overflow (Надо исправить)
9. .about → height: 595px — замечание о высоте блока (Надо исправить)
10. .logo-round → position: absolute — замечание об абсолютном позиционировании (Надо исправить)
11. .about_column → position: absolute — замечание об абсолютном позиционировании (Надо исправить)
12. footer → min-height: 180px — замечание о высоте блока (Надо исправить)
# index.html — добавлено 11 комментариев ревьюера
6. < button class="description-button" > — рекомендация указывать type="button" (Можно лучше)
7. Абзацы секции «Об аукционе» — замечание о том, что тексты могут меняться, и вёрстка должна оставаться гибкой (Надо исправить)
8. < address class="footer-adress"> — замечание о необходимости переиспользовать общий CSS-класс для контактов (Надо исправить)
9. < a href="#top" class="footer-menu-item no_inline"> — замечание о классе no_inline, привязанном к визуальной составляющей, рекомендация использовать класс типа link_active (Надо исправить)
10. < div class="socials"> — рекомендация использовать список ul li для семантики (Можно лучше)
11. Ссылки на соцсети — рекомендация добавить target="_blank" (Можно лучше)