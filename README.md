## Домашнее задание к занятию «Объектно-ориентированное программирование и проектирование»

**Цель задания**

Научиться проектировать объекты, имеющие и поля, и методы.

**Инструкция к заданию**

1. Скачайте и установите профессиональный редактор кода Intellij Idea Community Version.
1. Откройте IDEA и создайте и настройте новый Maven-проект. Под каждую задачу следует создавать отдельный проект, если
   обратное не сказано в условии.
1. Создайте пустой репозиторий на GitHub и свяжите его с папкой вашего проекта, а не с какой-либо другой.
1. Правильно настройте репозиторий в плане .gitignore. Проигнорируйте папки .idea и target (раньше была out) и
   .iml-файл — их в репозитории быть не должно.
1. Закоммитьте и запушьте созданный проект на ГитХаб, настройте GitHub Actions, сделайте git pull.
1. Выполните в IDEA требуемую задачу согласно условию.
1. Проверьте соблюдение правил форматирования кода.
1. Убедитесь, что при запуске mvn clean verify (раньше было mvn clean test) все тесты запускаются, проходят, а сборка
   завершается успешно.
1. Закоммитьте и отправьте в репозиторий содержимое папки проекта.
1. Убедитесь, что CI запустился на последнем коммите и завершился успешно — появилась зелёная галочка.

**Материалы, которые пригодятся для выполнения задания**

[Как создать Maven-проект в IDEA?](https://github.com/netology-code/javaqa-homeworks-video/blob/javaqa-55/QA_Maven_Idea_Create.md)

[Как отформатировать код в Java?](https://github.com/netology-code/javaqa-homeworks-video/blob/javaqa-55/QA_Java_Idea_Format.md)

[Как настроить CI на основе GitHub Actions?](https://github.com/netology-code/javaqa-homeworks-video/blob/javaqa-55/QA_CI.md)

**Задание 1 — обязательное**

В рамках проекта по созданию «Умного дома» у нас появился очень важный клиент, который хочет кастомную доработку: он
очень любит радио, поэтому нам нужно научиться управлять радио.

Что нужно сделать: по аналогии с кондиционером создайте класс Radio, в котором храните следующие поля — данные, которые
будут помнить о себе объекты радио:

* номер текущей радиостанции,
* громкость звука.

Требования к работе с радиостанциями

1. Номер текущей радиостанции может принимать значения только в пределах от 0 до 9.
1. Если текущая радиостанция 9 и клиент нажал на кнопку next (=вызвал одноимённый метод next, с англ. — следующая) на
   пульте, то текущей должна стать нулевая. В остальных случаях при нажатии на эту же кнопку радио переключается просто
   на следующую станцию.
1. Если текущая радиостанция 0 и клиент нажал на кнопку prev (=вызвал одноимённый метод prev, с англ. — предыдущая) на
   пульте, то текущей должна стать девятая. В остальных случаях радио переключается просто на предыдущую станцию.
1. Клиент должен иметь возможность выставлять номер радиостанции через прямое указание её номера. Для этого подойдёт
   один обычный метод-сеттер с проверкой на допустимость номера станции.

Требования к работе с уровнем громкости звука

1. Клиент должен иметь возможность увеличивать и уменьшать уровень громкости звука в пределах от 0 до 100.
1. Если уровень громкости звука достиг максимального значения, то дальнейшее нажатие на + (=вызов метода увеличения
   громкости на один, придумайте название сами) не должно ни к чему приводить.
1. Если уровень громкости звука достиг минимального значения, то дальнейшее нажатие на - (=вызов метода уменьшения
   громкости на один, придумайте название сами) не должно ни к чему приводить.

Пример реализации метода увеличения звука на 1. Остальные методы переключения на 1 текущей станции или звука сделайте
самостоятельно по аналогии:

```java
public class Radio {
  ...

    public void increaseVolume() {
        if (currentVolume < 100) {
            currentVolume = currentVolume + 1;
        }
    }
}
```

К созданному классу Radio напишите тесты, добейтесь покрытия на 100% по бранчам, обрушать сборку по покрытию при этом не
нужно. То есть настройте проект в режиме генерации отчётов. Для хорошего тестирования рекомендуем вам провести
тест-дизайн перед написанием тестов, так вы с большей вероятностью найдёте дефекты в вашем коде.

**Правила приёма работы**

Прикреплена одна ссылка на публичный репозиторий с решением задачи.

***

**Критерии оценки**

1. В каждом репозитории размещено содержимое папки проекта IDEA. Корнем репозитория должна быть именно папка проекта —
   не папка src, не папка внутри которой лежит папка проекта; таким образом в корне репозитория должна лежать сразу
   папка src.
2. Есть файл .gitignore, игнорирующий ненужные файлы и папки, которые должны отсутствовать в репозитории. Если они
   присутствуют, их нужно оттуда удалить.
1. Программа соответствует всем требованиям из условия задачи.
1. Программа использует только те инструменты языка, которые мы проходили или которые прямо разрешены условием задачи.
1. Программа работает правильно на всех примерах из условия.
1. Программный код отформатирован и соответствует пройденным требованиям к качеству кода.
1. При запуске mvn clean verify тесты запускаются и проходят, а сборка завершается успешно.
1. В репозитории настроен CI на основе GitHub Actions, и он успешно прошёл на последнем коммите.
1. Программа спроектирована достаточно логично и правильно, не противоречит общепринятым в производстве практикам и
   традициям.
1. При наличии недочётов, в зависимости от их серьёзности и количества, работа может быть отправлена на доработку или
   принята — решение принимается на основе экспертной оценки работы.

## Домашнее задание к занятию «Объекты с внутренним состоянием, управление состоянием при тестировании»

**Цель задания**

Научиться управлять начальным состоянием объектов через конструкторы.

**Инструкция к заданию**

1. Скачайте и установите профессиональный редактор кода Intellij Idea Community Version.
2. Возьмите проект с домашнего задания про Радио и создайте новую ветку flexible
1. Выполните в IDEA требуемую задачу согласно условию.
1. Проверьте соблюдение правил форматирования кода.
1. Убедитесь, что при запуске mvn clean verify (раньше было mvn clean test) все тесты запускаются, проходят, а сборка завершается успешно.
1. Закоммитьте и отправьте в репозиторий содержимое папки проекта.
1. Убедитесь, что CI запустился на последнем коммите и завершился успешно — появилась зелёная галочка.
   
**Материалы, которые пригодятся для выполнения задания**

1. [Как создать Maven-проект в IDEA?](https://github.com/netology-code/javaqa-homeworks-video/blob/javaqa-55/QA_Maven_Idea_Create.md)
2. [Как отформатировать код в Java?](https://github.com/netology-code/javaqa-homeworks-video/blob/javaqa-55/QA_Java_Idea_Format.md)
3. [Как настроить CI на основе Github Actions?]https://github.com/netology-code/javaqa-homeworks-video/blob/javaqa-55/QA_CI.md

**Задание 1 — обязательное**

Проект «Умный дом» развивается, и решено улучшить часть, отвечающую за радио.

Что нужно сделать: внедрить изменения в сам класс и тесты.

Как это сделать:

 * создайте в Git в том же репозитории новую ветку flexible — возьмите проект к ДЗ про радио, в который уже подключены CI и нужные плагины;
 * модифицируете класс Radio под новые требования;
 * делаете тест-дизайн новой версии класса, модифицируете или добавляете новые тесты;
 * пушите всё на GitHub и делаете pull request, мёржить его не нужно;
 * удостоверьтесь, что все тесты в CI запускаются на pull request и проходят;
 * ссылку на pull request пришлите в качестве результата ДЗ.
  
Требования к работе с радиостанциями

 1. Можно задавать количество радиостанций при создании объекта, по умолчанию — 10.
 1. Номер текущей радиостанции изменяется в пределах от 0 до количества радиостанций не включительно. То есть если станций 10, то номер последней — 9.
 1. Если текущая радиостанция — максимальная, и клиент нажал на кнопку next на пульте, то текущей должна стать нулевая.
 1. Если текущая радиостанция — 0, и клиент нажал на кнопку prev на пульте, то текущей должна стать максимальная.
 1. Всё так же должен присутствовать сеттер текущей станции.


Теперь объекты радио в своём поле будут хранить и количество станций, заданное при создании объекта радио. Для этого вам понадобится создать свой конструктор для класса Radio с одним параметром, принимающим желаемое количество радиостанций и сохраняющим это значение у себя в поле. Ещё один конструктор потребуется без параметров, чтобы, если пользователь нашего класса не захотел указывать количество радиостанций, мы бы выставили их количество в 10 штук, как указано в требованиях, «по умолчанию — 10».

Внимание: конструктором с параметром задаётся именно количество радиостанций, а не номер максимальной, это разные вещи — если количество станций, например, 30, то последней будет номер 29, так как нумеруем мы с нуля.

Требования к работе с уровнем громкости звука:

 * клиент должен иметь возможность увеличивать и уменьшать уровень громкости звука в пределах от 0 до 100;
 * если уровень громкости звука достиг максимального значения, то дальнейшее нажатие на + не должно ни к чему приводить;
 * если уровень громкости звука достиг минимального значения, то дальнейшее нажатие на - не должно ни к чему приводить.

Итог: ссылку на pull request пришлите в качестве результата ДЗ.

**Задание 2 — необязательное**

Пришла пора разобраться с [Lombok](https://projectlombok.org). В вашем личном кабинете прикреплено видео, в котором демонстрируется работа с Lombok.

Что нужно сделать

1. Из ветки flexible, созданной в предыдущем задании, создайте ветку lombok, в которой перепишите ваш класс Radio, используя Lombok.
1. Сделайте коммит и pull request на GitHub, удостоверьтесь, что CI успешно проводит сборку, мёржить его не нужно.
   
**Результат**

При отправке решения в личном кабинете прикрепите ссылку на ваш публичный репозиторий GitHub.

**Правила приёма работы** 

Прикреплено по ссылке на пул-реквест для каждой отправляемой задачи на проверку.

**Критерии оценки**

1. В каждом репозитории размещено содержимое папки проекта IDEA. Корнем репозитория должна именно папка проекта — не папка src, не папка внутри которой лежит папка проекта. В корне репозитория должна лежать сразу папка src.
1. Есть файл .gitignore, игнорирующий ненужные файлы и папки, которые должны отсутствовать в репозитории. Если они присутствуют, их нужно оттуда удалить.
1. Программа соответствует всем требованиям из условия задачи.
1. Программа использует только те инструменты языка, которые мы проходили или которые прямо разрешены условием задачи.
1. Программа работает правильно на всех примерах из условия.
1. Программный код отформатирован и соответствует пройденным требованиям к качеству кода.
1. При запуске mvn clean verify тесты запускаются и проходят, а сборка завершается успешно.
1. В репозитории настроен CI на основе GitHub Actions, и он успешно прошёл на последнем коммите.
1. Программа спроектирована достаточно логично и правильно, не противоречит общепринятым в производстве практикам и традициям.
1. При наличии недочётов, в зависимости от их серьёзности и количества, работа может быть отправлена на доработку или принята — решение принимается на основе экспертной оценки работы.