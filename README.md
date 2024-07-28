# Тестовое задание для Diginetica

## Верстка

**Запуск проекта**

```
cd layout

npm run serve
```

## JavaScript

1. **Каким будет результат следующей операции на языке JavaScript: [1, 2, 3] + [4, 5, 6]. Почему был получен такой результат?**

```
1,2,34,5,6
```
Оператор "+" преобразует массивы в строки, разделенные запятыми, из-за того что они не являются примитивами, после этого, строки конкатенируются

2. **Дано выражение:
var a = {b: 1};
var b = a;
b.b = 2;
console.log(a);
Что будет выведено в консоли? Почему был получен такой результат?**

```
{b: 1}
```
Консоль выводит {b: 2}, потому что a и b ссылаются на один и тот же объект. Изменения через одну из переменных видны и через другую.

3. **Написать регулярное выражение, совпадающее с числом с плавающей точкой с точностью до 3 знака после запятой.**

```
^-?\d+\.\d{1,3}$
```

4. **Написать регулярное выражение, по которому определяется является ли строка ссылкой. Объяснить, как оно работает.**

```
const isUrl = str => {
    const regex = /^(https?:\/\/)?([\w\d\-]+\.)+[a-z]{2,6}(:\d+)?(\/[\w\d\-\.]*)*\/?(\?[^\s]*)?(#[^\s]*)?$/;
    return regex.test(str);
}
```
```^``` - начало строки

```(https?:\/\/)?``` - Протокол - опциональный блок http:// или https://

```([\w\d\-]+\.)+``` - Домен - символы, цифры или тире, которые могут быть разделены точкой

```[a-z]{2,6}``` - Суффикс - от 2 до 6 букв в нижнем регистре

```(:\d+)?``` - Порт - опциональный блок для обозначения порта, " : " и одна или несколько цифр

```(\/[\w\d\-\.]*)*``` - Путь - " / " и 0 или более символов, цифр, тире или точек  для пути URL. " * " - блок сожет повторять 0 или более раз

```\/?``` - опциональный символ " / "

```(\?[^\s]*)?``` - Параметры - начало строки запроса " ? " и сам запрос, содержащий 0 или более символов, кроме пробелов, опционально

```(#[^\s]*)?``` - Фрагмент - начало фрагмента url и ноль или более символов, кроме пробелов, опционально

```$``` - конец строки

5. **Каким будет значение переменной text после выполнения данного JavaScript кода? 
function setText(message) { 
text = message;
 }
 var text = 'Текст';
 setText('Сообщение');
Опишите, почему получился такой результат.**

```
Сообщение
```
Переменная text задается глобально, затем, в результате работы функции ей присваивается другое значение

6. **Написать функцию для получения список всех артикулов товаров в консоли браузера на странице https://groupprice.ru/categories/jenskaya-odejda?referer_from=main_catalog**

```
function getArticleNumbers() {
    const products = document.querySelectorAll('._product');
    let articleNumbers = [];
    for (const product of products) {
        articleNumbers.push(product.getAttribute('data-id'));
    }
    return articleNumbers;
}
```

7. **Написать функцию для получения всех характеристики товара в консоли браузера в виде объекта в формате attributeName: value на странице https://nir-vanna.ru/product/smesitel-bravat-art-f175109c-dlya-rakoviny/**

```
function getProductCharacters() {
    const characters = document.querySelectorAll('.tab-pane-product-parameter-item');
    let productCharacters = {};
    for(const char of characters) {
        const attributeName = char.querySelector('.parameter-name').firstChild.textContent.trim();
        const value = char.querySelector('.parameter-value').textContent;
        productCharacters[attributeName] = value.trim();
    }
    return productCharacters;
}
```





