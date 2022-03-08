# hse_hw2_chip

Ссылка на колаб: https://colab.research.google.com/drive/1E_tW74_XhvedGc9IWk1C6O8K3zXkPab4?usp=sharing
Клеточная линия PC-3, гистоновая метка H2AFZ 
Реплики ENCFF598PWF, ENCFF700QWJ; контроль ENCFF829PCB

### FastQC-анализ исходных файлов

Контроль (ENCFF829PCB)

![](https://github.com/kolbunovaa/images/blob/main/PCB1.png)

![](https://github.com/kolbunovaa/images/blob/main/PCB2.png)

Первая реплика (ENCFF598PWF)

![](https://github.com/kolbunovaa/images/blob/main/PWF1.png)

![](https://github.com/kolbunovaa/images/blob/main/PWF2.png)

Вторая реплика (ENCFF700QWJ)

![](https://github.com/kolbunovaa/images/blob/main/QWJ1.png)

![](https://github.com/kolbunovaa/images/blob/main/QWJ2.png)

Как видно качество по основаниям во всех трех файлах хороший, в контроле и первой реплике есть проблемы с per tiles sequence: в некоторых позициях (теплые цвета) в ридах есть проблемы с качеством. В следующих параметрах все более менее нормально: во всех файлах стоит предупреждение в GC-содержании и частотах встречаемости каждого нуклеотида; оставшиеся параметры в порядке

### После подрезания чтений:
Контроль (ENCFF829PCB)

![](https://github.com/kolbunovaa/images/blob/main/PCB_trimm1.png)

![](https://github.com/kolbunovaa/images/blob/main/PCB_trimm2.png)

Первая реплика (ENCFF598PWF)

![](https://github.com/kolbunovaa/images/blob/main/PWF_trimm1.png)

![](https://github.com/kolbunovaa/images/blob/main/PWF_trimm2.png)

После процедуры подрезания (с помощью trimmomatic) per tiles sequence quality улучшилось, но все равно есть предупреждение; также рer base sequence quality стало тоже выглядеть симпатичнее, хотя и до этого там не было проблем. Предупреждения, относящиеся к содержанию нуклеотидов и их встречаемости, остались, но по-моему мы на это повлиять особо не можем

### Статистика по образцам
|  | ENCFF829PCB | ENCFF598PWF | ENCFF700QWJ |
| --- | --- | --- | --- |
|Кол-во ридов |42549155|38836404|73984712|
|Кол-во уникально картированных ридов|2020174 (4.75%)|1792482 (4.62%)|3599228 (4.86%)|
|Кол-во неуникально картированных ридов|5200776 (12.22%)|4311831 (11.10%)|8727635 (11.80%)|
|Кол-во некартированных ридов|35328205 (83.03%)|32732091 (84.28%) |61657849 (83.34%) |

Такой большой процент некартированных чтений связан с тем, что выравнивание происходило только на одну хромосому

### Диаграммы Венна
#### ENCFF598PWF
|  |  |
| --- | --- |
|![](https://github.com/kolbunovaa/images/blob/main/PWF_peak1.png)|![](https://github.com/kolbunovaa/images/blob/main/PWF_peak2.png)|

#### ENCFF700QWJ
|  |  |
| --- | --- |
|![](https://github.com/kolbunovaa/images/blob/main/QWJ_peak1.png)|![](https://github.com/kolbunovaa/images/blob/main/QWJ_peak2.png)|

Такое небольшое количество пересечений связано опять же с тем, что мы проводили выравнивание на одну хромосому, тогда как в ENCODE взяты все хромосомы. Пересечения наши пики/ENCODE и ENCODE/наши пики различны потому, что из первого множества считываются куски, которые есть также и во втором множестве. Понятное дело, если сначала брать наши пики, то процент (от первого множества, т. е. от наших пиков) попавших в пересечение будет больше. Если же брать первым ENCODE, то очевидно, что процент пиков, попавших на пересечение будет меньше (так как в ENCODE все хромосомы, а совпадает только часть от одной хромосомы)

### Бонус
![](https://github.com/kolbunovaa/images/blob/main/h2afz.png)
|  |  |
| --- | --- |
|![](https://github.com/kolbunovaa/images/blob/main/result.png)|![](https://github.com/kolbunovaa/images/blob/main/result2.png)|

Графики распределения гистоновой метки H2AFZ имеют пик почти в самом начале, который затем постепенно затухает на протяжении всего расстояния. Данный вид аналогичен тому, что изображено на картинке, предложенной нам для сравнения


