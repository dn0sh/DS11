# DAY 11 – Прикладная статистика
## Оглавление
1. [Глава I](#глава-i) \
    1.1. [Преамбула](#преамбула)
2. [Глава II](#глава-ii) \
    2.1. [Общая инструкция](#общая-инструкция)
3. [Глава III](#глава-iii) \
    3.1. [Цели](#цели)
4. [Глава IV](#глава-iv) \
    4.1. [Задание](#задание)
5. [Глава V](#глава-v) \
    5.1. [Сдача работы и проверка](#сдача-работы-и-проверка)

## Глава I
### Преамбула
Прикладная статистика – это наука, которая применяет методы математической статистики для решения задач в различных 
областях, таких как экономика, медицина, социология, психология и т.д. 
Вот некоторые из методов прикладной статистики:
* Анализ дисперсии – это метод, который используется для определения статистически значимых различий между группами данных.
Он может быть использован для сравнения средних значений между группами или для проверки наличия эффекта 
влияния факторов на результаты.
* Корреляционный анализ – это метод, который используется для изучения связей между двумя или более переменными. 
Он может быть использован для определения степени связи между переменными и для выявления 
возможных причинно-следственных связей.
* Многомерный статистический анализ – это метод, который используется для анализа данных с несколькими переменными. 
Он может быть использован для изучения сложных связей между переменными и для выявления скрытых факторов, 
которые могут влиять на результаты.
* Статистический контроль качества – это метод, который используется для определения соответствия производственных 
процессов заданным стандартам. Он может быть использован для контроля качества продукции или услуг и для выявления
причин некачественной продукции.

## Глава II
### Общая инструкция

Методология Школы 21 может быть не похожа на тот образовательный опыт, который случался с тобой ранее. Её отличает высокий уровень автономии: у тебя есть задача, ты должен её выполнить. По большей части, тебе нужно будет самому добывать знания для её решения. Второй важный момент — это peer-to-peer обучение. В образовательном процессе нет менторов и экспертов, перед которыми ты защищаешь свой результат. Ты это делаешь перед таким же учащимися, как и ты сам. У них есть чек-лист, который поможет им качественно выполнить приемку вашей работы.

Роль Школы 21 заключается в том, чтобы обеспечить через последовательность заданий и оптимальный уровень поддержки такую траекторию обучения, при которой ты не только освоишь hard skills, но и научишься самообучаться.

- Не доверяй слухам и предположениям о том, как должно быть оформлено ваше решение. Этот документ является единственным источником, к которому стоит обращаться по большинству вопросов;
- твое решение будет оцениваться другими учащимися;
- подлежат оцениванию только те файлы, которые ты выложил в GIT (ветка develop, папка src);
- в твоей папке не должно быть лишних файлов — только те, что были указаны в задании;
- не забывай, что у вас есть доступ к интернету и поисковым системам;
- обсуждение заданий можно вести и в Rocket.Chat;
- будь внимателен к примерам, указанным в этом документе — они могут иметь важные детали, которые не были оговорены другим способом;
- и да пребудет с тобой Сила!



## Глава III
### Цели
В этом проекте ты познакомишься с доверительными интервалами, А/Б-тестами и корреляционным анализом.

## Глава IV
### Доверительные интервалы
Сегодня тебе предстоит попробовать себя в роли бизнес-аналитика в одной из сети пиццерий. 
Твоя задача - улучшить работу ресторана. Нам известны [данные о заказах пиццы](datasets/pizza.csv) - давайте их изучим.

#### Задание 1
Давай загрузим [данные о заказах](datasets/pizza.csv). Построй гистограмму зависимости количества проданной пиццы от дня 
недели. Выведи дни недели, в которые продано больше и меньше всего пиццы.

#### Задание 2
Посчитай, сколько **секунд** необходимо для приготовления каждой пиццы по всем заказам. 
Значения сохранить в новый столбец - `cook_time`. Найти среднее, медианное, максимальное и минимальное время 
приготовления пиццы. Результат округлите до целого.

#### Задание 3
Построй 95% доверительный интервал для среднего времени приготовления пиццы.
> Для расчета стандартного отклонения используй `numpy.std(ddof=1)`

#### Задание 4
Хозяин ресторана хочет оптимизировать меню ресторана. При формировании цены на пиццу хозяин хочет учитывать время 
её изготовления. Давай найдем ту пиццу (pizza_name), у которой верхняя граница доверительного интервала её изготовления 
самая высокая.
> Среди пицц, у которых за все время заказывали более 100 штук

#### Задание 5
Также хозяину ресторана хочется убрать из меню пиццы с нестабильным временем изготовления. 
Давай найдем пиццу с самым широким доверительным интервалом.
> Среди пицц, у которых за все время заказывали более 100 штук

### АВ тестирование
В данной задаче тебе предстоит выяснить, какая реклама больше всего нравится покупателю. В отделе маркетинга решили, 
что для повышения продаж необходимо обновить рекламный баннер. Дизайнеры добавили милых котиков и думают, что 
на этот баннер будет откликаться большее количество людей. Чтобы опровергнуть или подтвердить предположения
маркетологов и дизайнеров, попросили посетителей сайта проголосовать, какой баннер им нравится больше: новый или старый. 
На основе этого была собрана [статистика](datasets/click.csv), (banner_a - старый баннер, banner_b - новый) которую тебе
и предстоит проанализировать!

#### Задание 6 
В качестве нулевой гипотезы (H0) выберем, что старый баннер лучше нового.  В качестве альтернативной гипотезы (H1) выберем, 
что новый баннер лучше старого. Построй 95% доверительный интервал для доли каждого из баннеров, используя метод 
[proportion_confint](https://www.statsmodels.org/devel/generated/statsmodels.stats.proportion.proportion_confint.html)
библиотеки statsmodels. Пересекаются ли эти интервалы?

#### Задание 7
Для более детальной оценки построй 95% доверительный интервал для разности двух долей.
**Ответ дай в формате:**\
95% доверительный интервал для разности двух долей: [0.99847, 9.99847]

#### Задание 8
Проведи АБ-тест. Какой баннер лучше? H0 - Старый баннер или H1 - новый баннер.
В этом тебе поможем функция [z-критерия](code-samples/stats.py).

### Корреляции

#### Задание 9
Прочитай про корреляции Пирсона и Спирмена. Узнай какие связи между выборками они способны находить. 
По сгенерированным выборкам посчитай коррелицию Пирсона и Спирмена для выборок `x-y1`, `x-y2`, `x-y3`. 
Отрисуй выборки в формате, как показано ниже:
<img src="misc/images/corr.png">
Объясни, почему получается такое значение корреляций.

#### Задание 10
Построй облако из тысячи точек c помощью приведенного кода.
Выведи значения коэффициентов корреляции.
Случайным образом выбери четыре точки. Каждую из точек передвигать в правый верхний угол относительно облака точек 
(тем самым создавая выброс):
значения по оси х 25, 50, 150, 650
по оси y 20, 40, 60, 80.
Выводи на графике перемещения точек.
Для каждого расстояния рассчитай коэффициент корреляции Пирсона и Спирмана.
Какая корреляция больше устойчива к выбросам?


## Глава V
### Сдача работы и проверка

1. Сохрани решения в файл 11-assigment.ipynb.
2. Загрузи изменения на Git в ветку develop.

💡 [Нажми здесь](https://forms.gle/Fcjm723LECFPPdZj6) **чтобы отправить обратную связь по проекту**. 
