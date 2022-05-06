# План автоматизации тестирования сценария перехода к форме записи и заполнения этой формы

## Автоматизируемые сценарии:
1. Переход к форме записи на курс с главной страницы через «Каталог курсов»

        1 На главной странице нажать «Каталог курсов».
        2 В выпадающем списке навести курсор на раздел «Программирование».
        3 В списке справа нажать на «Тестировщик ПО».
        4 В открывшейся странице нажать кнопку «Записаться».

1. Переход к форме записи на курс с главной страницы через «Направления обучения»

        1 На главной странице нажать «Каталог курсов».
        2 В выпадающем списке навести курсор на раздел «Программирование».
        3 В списке справа нажать на «Тестировщик ПО».
        4 В открывшейся странице нажать кнопку «Записаться».
        
1. Валидация поля "Имя" формы записи на курс
        
        1 Предусловия: открыта форма записи на курс.
        2 Ввести одну букву на кириллице (ожидаемый результат: Поле подсвечено. Есть подсказка "Должно быть не короче 2 символов").
        3 Ввести две буквы на кириллице (ожидаемый результат: Текст принят).
        4 Ввести составное имя через дефис на кириллице. Например: "Анна-Мария". (ожидаемый результат: Текст принят).
        5 Ввести составное имя через пробел на кириллице. Например: "Анна Мария" (ожидаемый результат: Текст принят).
        6 Ввести одну букву на латинице (ожидаемый результат: Поле подсвечено. Есть подсказка "Должно быть не короче 2 символов").
        7 Ввести две буквы на латинице (ожидаемый результат: Текст принят).
        8 Ввести составное имя через дефис на латинице. Например: "Anna-Maria". (ожидаемый результат: Текст принят).
        9 Ввести составное имя через пробел на латинице. Например: "Anna Maria" (ожидаемый результат: Текст принят).
        10 Ввести имя с буквой "ё". Например: "Семён" (ожидаемый результат: Текст принят).
        11 Ввести цифры (ожидаемый результат: Поле подсвечено. Есть подсказка "Должно состоять из букв").
        12 Ввести спецсимволы (ожидаемый результат: Поле подсвечено. Есть подсказка "Должно состоять из букв").
        
1. Валидация поля "Телефон" формы записи на курс
        
        1 Предусловия: открыта форма записи на курс.
        2 Ввести три цифры (ожидаемый результат: Поле подсвечено. Есть подсказка "Номер в формате +9 (999) 999-99-99").
        3 Ввести десять цифр (ожидаемый результат: Поле подсвечено. Есть подсказка "Номер в формате +9 (999) 999-99-99").
        4 Ввести одиннадцать цифр ((ожидаемый результат: Номер принят).
        5 Ввести двенадцать цифр (ожидаемый результат: Поле подсвечено. Есть подсказка "Номер в формате +9 (999) 999-99-99").
        6 Ввести буквы на кириллице (ожидаемый результат: Поле подсвечено. Есть подсказка "Номер в формате +9 (999) 999-99-99").
        7 Ввести буквы на латинице (ожидаемый результат: Поле подсвечено. Есть подсказка "Номер в формате +9 (999) 999-99-99").
        8 Ввести спецсимволы (ожидаемый результат: Поле подсвечено. Есть подсказка "Номер в формате +9 (999) 999-99-99").
        
1. Отправка пустой формы

        1 Предусловия: открыта форма записи на курс.
        2 Нажать кнопку «Записаться».
        3 Ожидаемый результат: Форма не отправлена. Поля подсвечены. Есть подсказка "Обязательное поле".
        
1. Отправка формы с невалидным значением поля "Имя"

        1 Предусловия: открыта форма записи на курс.
        2 Заполнить имя невалидными данными (например: ввести цифры).
        3 Заполнить телефон валидными данными (например: +79039998877).
        4 Нажать кнопку «Записаться».
        5 Ожидаемый результат: Форма не отправлена. Поле "Имя" подсвечено. Под полем есть подсказка "Должно состоять из букв".
        
1. Отправка формы с невалидным значением поля "Телефон"

        1 Предусловия: открыта форма записи на курс.
        2 Заполнить имя валидными данными (например: "Анна").
        3 Заполнить телефон невалидными данными (например: ввести буквы).
        4 Нажать кнопку «Записаться».
        5 Ожидаемый результат: Форма не отправлена. Поле "Телефон" подсвечено. Под полем есть подсказка "Номер в формате +9 (999) 999-99-99".
        
1. Отправка формы с валидными значениями полей

        1 Предусловия: открыта форма записи на курс.
        2 Заполнить имя валидными данными (например: "Анна").
        3 Заполнить телефон валидными данными (например: "+79018887766").
        4 Нажать кнопку «Записаться».
        5 Ожидаемый результат: Форма отправлена. Есть сообщение об успешной отправке формы.

## Перечень используемых инструментов с обоснованием выбора:
- Java (Кросс-платформенность, дружественный синтаксис, объектно-ориентированный язык).
- IntelliJ IDEA (Понимает код на языке Java. Предлагает варианты автоматического дополнения кода (как правило, именно тот, который и имел в виду пользователь), мгновенно показывает ошибки и потенциальные проблемы в написанном коде, умеет сама их исправлять).
- Gradle (Более быстрая сборка по сравнению с Maven).
- Selenide (Основан на Selenium WebDriver и дает преимущества перед Selenium). 
- Chrome (Наиболее распространенный браузер).
- Allure (Построение подробных и понятных отчётов автотестов. Возможность различных группировок тестов по тест-классам. Возможность построения единого отчёта, независимо от используемого фреймворка тестирования).
- GitHub (Ориентирован на общедоступный код. Бесплатный).

## Перечень необходимых разрешений/данных/доступов:
- Для выполнения автоматизации сценариев нужно разрешение на тестирование и автоматизацию.
- Для заполнения полей формы как валидными, так и невалидными данными воспользуемся библиотекой Faker.

## Перечень и описание возможных рисков при автоматизации:

1. Риск: отсутствуют требования к проекту.

   Возможные последствия: изменение структуры сайта в ходе реализации проекта. Корректировка авто-тестов. Срыв сроков выпуска проекта.
   
1. Риск: изменение структуры сайта в ходе реализации проекта.

   Возможные последствия: Корректировка авто-тестов. Срыв сроков выполнения тестирования.
   
1. Риск: разработка паралельно тестированием.

   Возможные последствия: тестировщик будет часто переделывать авто-тесты.
   
1. Риск: срыв сроков выполнения тестирования.

   Возможные последствия: финансовые потери, утрата репутации, уменьшение клиентов.

1. Риск: маленький опыт тестировщика.

   Возможные последствия: функциональность может быть недостаточно хорошо протестирована. Могут быть пропущены баги.

1. Риск: нестабильные тесты.

   Возможные последствия: могут быть пропущены баги.

1. Риск: долгая починка багов.

   Возможные последствия: Замедление выпуска задач. Останется меньше времени на тестирование. Срыв сроков выполнения тестирования. Пропуск багов.
   
1. Риск: слишком много багов.

   Возможные последствия: не хватит времени на отлов всех багов. Утрата репутации.

1. Риск: проблемы с поиском локаторов.

   Возможные последствия: долгое написание авто-тестов. Срыв сроков выполнения тестирования.  
   
1. Риск: долгое и дорогое создание авто-тестов.

   Возможные последствия: не будет окупаемости авто-тестов.

1. Риск: 1 специалист в команде.

   Возможные последствия: при отсутствии специалиста (больничный, отпуск, увольнение) произойдет срыв сроков тестирования. Финансовые потери, утрата репутации.
   
1. Риск: дорогая поддержка авто-тестов. 

   Возможные последствия: не будет окупаемости авто-тестов.
   
1. Риск: отсутствие требуемых доступов и разрешений. 

   Возможные последствия: невозможно выполнить тестирование.
   
1. Риск: проблема с подготовкой тестового окружения. 

   Возможные последствия: невозможно выполнить тестирование.
   
1. Риск: нехватка бюджета. 

   Возможные последствия: отсутствие тестирования.

## Перечень необходимых специалистов для автоматизации:

Требуется тестировщик-автоматизатор со знанием языка программирования Java.

## Интервальная оценка с учётом рисков:

На автоматизацию сценариев будет затрачено 8 – 10 часов.

