# <center> **Прогнозирование риска сердечного приступа**

![](https://image.shutterstock.com/image-vector/heart-attack-risk-factors-vector-260nw-550350928.jpg)

Проект основан на данных с платформы Kaggle [Heart Attack Risk Prediction](https://www.kaggle.com/datasets/iamsouravbanerjee/heart-attack-prediction-dataset/data)

Набор данных для прогнозирования риска сердечного приступа служит ценным ресурсом для изучения сложной динамики здоровья сердца и его предикторов. Сердечные приступы или инфаркты миокарда продолжают оставаться серьезной глобальной проблемой здравоохранения, что требует более глубокого понимания их предшественников и потенциальных смягчающих факторов. Этот набор данных включает в себя широкий спектр атрибутов, включая возраст, уровень холестерина, артериальное давление, привычку курить, характер физических упражнений, диетические предпочтения и многое другое, с целью выяснить сложное взаимодействие этих переменных при определении вероятности сердечного приступа. Применяя прогнозную аналитику и машинное обучение для этого набора данных, исследователи и специалисты здравоохранения могут разрабатывать упреждающие стратегии профилактики и лечения сердечно-сосудистых заболеваний. Набор данных является свидетельством коллективных усилий, направленных на улучшение нашего понимания здоровья сердечно-сосудистой системы и прокладывание пути к более здоровому будущему.

Этот набор данных предоставляет полный набор характеристик, имеющих отношение к здоровью сердца и выбору образа жизни, включая специфичные для пациента детали, такие как возраст, пол, уровень холестерина, артериальное давление, частота сердечных сокращений и такие показатели, как диабет, семейный анамнез, привычка к курению, ожирение и потребление алкоголя. Кроме того, учитываются факторы образа жизни, такие как часы физических упражнений, пищевые привычки, уровень стресса и сидячий образ жизни. Учитываются медицинские аспекты, включающие предыдущие проблемы с сердцем, использование лекарств и уровень триглицеридов. Социально-экономические аспекты, такие как доход и географические атрибуты, такие как страна, континент и полушарие, включены. Набор данных, состоящий из 8763 записей пациентов со всего мира, завершается важной функцией бинарной классификации, обозначающей наличие или отсутствие риска сердечного приступа, предоставляя комплексный ресурс для прогнозного анализа и исследований в области сердечно-сосудистых заболеваний.

+ Patient ID - Идентификатор пациента
+ Age - Возраст пациента
+ Sex - Пол
+ Cholesterol - Уровень холестерина
+ Blood Pressure - Кровяное давление (systolic/diastolic)
+ Heart Rate - Частота сердечных сокращений (пульс)
+ Diabetes - Есть ли у пациента диабет (Yes/No)
+ Family History - Семейный анамнез проблем с сердцем (1: Yes, 0: No)
+ Smoking - Курение (1: Smoker, 0: Non-smoker)
+ Obesity - Ожирение (1: Obese, 0: Not obese)
+ Alcohol Consumption - Употребление алкоголя (None/Light/Moderate/Heavy)
+ Exercise Hours Per Week - Количество часов физических упражнений в неделю
+ Diet - Пищевые привычки пациента (Healthy/Average/Unhealthy)
+ Previous Heart Problems - Предыдущие проблемы с сердцем пациента (1: Yes, 0: No)
+ Medication Use - Использование медицинских препаратов пациентом (1: Yes, 0: No)
+ Stress Level - Уровень стресса, о котором сообщил пациент (1-10)
+ Sedentary Hours Per Day - Количество часов сидячей деятельности в день
+ Income - Уровень дохода пациента
+ BMI - Индекс массы тела
+ Triglycerides - Уровень триглицеридов у пациента
+ Physical Activity Days Per Week - Количество физически активных дней в неделю
+ Sleep Hours Per Day - Количество часов сна в день
+ Country - Страна пациента
+ Continent - Континент, где проживает пациент
+ Hemisphere - Полушарие, где проживает пациент
+ Heart Attack Risk - Наличие риска сердечного приступа (1: Yes, 0: No) - Таргет

## <center> **Перебалансировка классов**

Для улучшения качества обучения модели была проведена перебалансировка классов, чтобы в выборке было одинаковое количество классов 1 и 0.

Проблема работы с несбалансированными наборами данных заключается в том, что большинство методов машинного обучения игнорируют класс меньшинства и, в свою очередь, имеют низкую производительность.

В SMOTE (техника синтезированной миноритарной передискретизации) мы создаем элементы в непосредственной близости от существующих в меньшем наборе.

Используя SMOTE, синтетические выборки генерируются следующим образом: берут разницу между рассматриваемым вектором признаков и его ближайшим соседом. Мы умножаем эту разницу на случайное число от 0 до 1 и добавляем его к рассматриваемому вектору признаков.

Это вызывает выбор случайной точки на отрезке линии между двумя конкретными объектами. Такой подход фактически вынуждает класс меньшинства принимать более общие решения.


## <center> **Генерация синтетических данных**

Компании часто сталкиваются с проблемой, когда им не хватает реальных данных или они не могут использовать реальные данные из соображений конфиденциальности. Здесь на помощь приходит генерация синтетических данных. Исследователи и специалисты по обработке данных используют синтетические данные для создания новых продуктов, повышения производительности моделей машинного обучения, замены конфиденциальных данных и экономии затрат на получение данных. Подробнее читайте в The Ultimate Guide to Synthetic Data .

Синтетические данные используются в секторе здравоохранения, беспилотных автомобилях, финансовом секторе, обеспечивая высокий уровень конфиденциальности, а также в исследовательских целях.

В данном случае, увеличение выборки за счет синтетических данных необходимо для решения проблемы переобучения модели.

Для создания синтетических табличных данных мы будем использовать условные генеративно-состязательные сети из библиотек Python с открытым исходным кодом под названием CTGAN.

Получился следующий баланс классов.

## <center> **Обучение модели**

### Метрики

**Сбалансированная точность (Balanced Accuracy)**

В случае дисбаланса классов есть специальный аналог accuracy – сбалансированная accuracy - это среднее полноты всех классов, ну или в других терминах: среднее чувствительности (Sensitivity) и специфичности (Specificity).:

$BA = \frac{R_1 + R_0}{2} = \frac{1}{2}(\frac{TP}{TP + FN} + \frac{TN}{TN + FP})$

Accuracy показывает количество правильно проставленных меток класса (истинно положительных и истинно отрицательных) от общего количества данных.

**Recall (true positive rate)**

В русском языке для этого термина используется слово «полнота» или «чувствительность». Эта метрика определяет количество истинно положительных среди всех меток класса, которые были определены как «положительный» и вычисляется по следующей формуле

$Recall = \frac{TP}{TP + FN}$

При определении риска инфаркта цена ошибки нераспознания положительного класса слишком велика, поэтому используем эту метрику.

### Модели

1. Логистическая регрессия
2. Полиномиальная логистическая регрессия
3. Метод опорных векторов
4. K-ближайших соседей
5. Дерево решений
6. Случайный лес
7. Градиентный бустинг
8. XGBoost

## <center> **Заключение**

Из рассмотренных алгоритмов лучший результат в решении задачи классификации риска инфаркта показал XGBoost. 

Метрика Balanced Accuracy на тренировочной выборке = 0.71, а на тестовой - 0.70. Таким образом, модель 70% случаях будет относить пациента к правильному классу.

Метрика Recall используется для того, чтобы минимизировать риск нераспознания положительного класса. На тренировочной выборке она равна 0.82, а на тестовой - 0.81. Модель правильно определяет пациента с риском инфаркта в 81% процентах случаев. Это хорошее значение метрики, но для медицинских данных нужно стремитьтся к лучшему показателю.

Наиболее значимыми признаками при обучении можели стали ожирение, употребление алкоголя, полушарие, здоровая диета и диабет. Все три группы признаков оказали воияние на обучение, но в первую очередь - здоровый или нездоровый образ жизни.