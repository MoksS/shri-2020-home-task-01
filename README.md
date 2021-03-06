# shri-2020-home-task-01

### Использованные инструменты

- **Webpack** - для сборки итогового css бандла
- **Sass** - для удобства написания кода по БЭМ-методологии

### Файловая структура
Html страницы и собранный css-бандл лежат в папке `build`.

Все блоки описаны в отдельных файлах `.scss`, расположенных в `src/styles/blocks/`. Имена файлов совпадают с именами блоков.

## Ответы на вопросы
### правильное использование БЭМ-сущностей
- **_какие части макета являются одним и тем же блоком?_**
1) Кнопки на стартовой странице `index.html`, странице `settings.html` и `build-history.html`.
![Кнопки](buttons.png)
2) Header и footer на каждой странице являются одним и тем-же блоком
3) Карточки с описанием коммита на станицах `build-history.html` и `build-details.html`.
4) Блоки `text` с различными модификаторами встречаются во многих местах на каждой странице.

- **_какие стили относятся к блокам, а какие к элементам и модификаторам?_**

Согласно БЭМ методологии, **блок** - это функционально независимый компонент страницы, который может быть переиспользован, **элемент** - составная часть блока, которая не может быть использована в отрыве от него, **модификатор** - сущность, определяющая внешний вид, состояние или поведение блока либо элемента.

Выбирая, что сделать блоком, а что элементом, я исходил из того, используется ли данная сущность где-то ещё, в отрыве от родительского блока. Если да, то я создавал новый блок, если нет, то элемент. 

- **_где нужно использовать каскады и почему?_**

Я постарался свести использование каскадов к минимуму, поскольку они усложняют код и могут затруднять его дальнейшее сопровождение. На мой взгляд их стоит использовать, только если требуется реализовать какое-то сложное поведение для определенной сущности в единственном месте. В таком случае проще использовать каскад, чем создавать дополнительные модификаторы или элементы. 

В данной работе я использовал каскадирование, чтобы сделать всплывающую при наборе текста в инпуте иконку очистки. Идея была в том, что когда в инпуте пропадает плейсхолдер, иконка переходит из состояния `display: none` в `display: block`. Это всё происходит в блоке `form-group`.

### консистентность
- **_какие видите базовые и семантические константы?_**

В базовые константы следует занести цвета используемой на странице палитры.

Семантическими константами следует сделать цвета текста, фона, кнопок, бордеров, размеры шрифтов, линьяж, начертания, размеры отступов, максимальную ширину контента и размеры скруглений.

Все константы у меня хранятся в файле `src/styles/_variables.scss`. 

- **_какие видите закономерности в интерфейсе?_**



### адаптивность
- **_где видите вариативность данных и как это обрабатываете?_**



- **_какие видите особенности, связанные с размером экрана?_**



Мне не очень нравится, как выглядят страницы на широкоформатных мониторах. Надо бы сделать область контента пошире, увеличить размеры шрифта и некоторых элементов контента. Пока не успел это реализовать, только занёс в TODO-лист.

- **_что еще повлияло на вашу вёрстку?_**

В контексте адаптивности, помимо вышенаписанного ничего не повлияло.

Ну а в целом на мою верстку повлияли сжатые сроки. Боясь всё не успеть, я почти сразу взялся за реализацию, хотя стоило больше времени уделить на предварительное продумывание БЭМ сущностей. В результате довольно времени ушло на исправления и переделывания.

**Даю согласие на упоминание моей работы на лекции по разбору задания**

## TODO
- карточка с описанием коммита - остаток сообщения, не умещающийся на одной строке должен обрезаться с троеточием
- сделать константы для отступов
- сделать блоки с заголовками
- адаптировать верстку для широкоформатных экранов
