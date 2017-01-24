# Test Randomizer

## Опис

Test Randomizer дозволяє розбити тести на довільну кількість варіантів та тестових питань, а такох ввивести перелік номерів вірних відповідей. 

## Швидкий старт

- запустити test.html
- обрати файл з базою тестів test.txt
- ввести кількість необхідних варіантів
- ввести кількість необхідних тестів в одному варіанті
- отримати задоволення від результату 8)

## Формування бази тестів

Інструкція описана із врахуванням того, що база тестів знаходистья у текстовому редакторі Word.
Для зручності користувасів все зроблено в одному HTML-файлі - test.html
Перевірити роботу Test Randomizer можна за допомогою пробної бази тестів test.txt
Базою тестів для Test Randomizer є txt-файл у кодуванні UTF-8.
	Формат тексту файлу: 
```
Вірна відповідь № 4
хибна відповідь;
хибна відповідь;
хибна відповідь;
#вірна відповідь.

Вірна відповідь № 3
хибна відповідь;
хибна відповідь;
#вірна відповідь;
хибна відповідь.
``` 

### 1. Попереднє форматування тестів у редакторі Word.

Шрифт правильної відповіді зазвичай позначають червоним кольором.

Забрати нумерацію усіх списків.
Між тестовими питаннями має бути пустий рядок (без пробілу).
В кінці документа не має бути пустого рядка (буде сприйнято за ще один варіант відповіді).

Для проставлення символа # перед правильними відповідями (позначеними червоним) можна скористатись макросом:
```
	Sub my()
	With ActiveDocument.Range.Find
	    .Font.ColorIndexBi = wdRed
	   
	    '.Text = "#"
	    Do While .Execute
	        .Parent.Paragraphs(1).Previous(0).Range.InsertBefore ("#")
	    Loop
	End With
	End Sub
```
Скопіювати текст в стандартний текстовий редактор Windows – “Notepad” або аналогічний, який дозволяє обирати формат кодування символів тексту.
Зберегти текст (обрати кодування utf-8).
