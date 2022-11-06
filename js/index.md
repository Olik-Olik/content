---
title: "Blur()"
description: "Событие blur. Пользователь ушел с события focus, потерял фокус и получил событие blur."
authors:
- Olik-Olik
  related:
- ""
  tags:
- doka
---
<!--
1. В description есть описание для соцсетей и поисковиков, не больше 200 символов
2. В authors есть ники авторов основного текста
3. В contributors перечислены ники всех соавторов и тех, кто работал над текстом (дописали «На практике»? Переписали блок? Вам сюда)
4. В keywords записаны ключевые слова для SEO: пишем сюда слова или фразы, которых нет в тексте статьи, но по ним могут искать этот материал
5. Удалены все пустые теги в шапке
6. Подпапка автора есть в папке _people/_
7. Демки лежат в подпапке _demos/_
8. В related добавлено три ссылки на материалы Доки, которые будут предлагаться в конце. Не добавляем следующий или предыдущий материал в разделе
-->

## Кратко

##Событие blur

```Пользователь кликает по элементу формы – происходит событие focus. Пользователь ушел с этого элемента в другое  место экрана с помощью мышки или клавиши :tab , происходит потеря фокуса или``` <span style="color:blue">событие blur</span>.

```Наша задача: визуально отследить``` <span style="color:blue"> событие blur</span>.

## Пример

```Визуально проверяем отсутствие фокуса на элементе input.```
```Есть два  поля ввода "Имя" , "Фамилия" ```.
```При  выборе элемента "Фамилия"  (событие focus)  документ ``` <span style="color:red"> красный</span>, ``` (при потере фокуса``` <span style="color:blue"> - событие blur)</span> документ <span style="color:green">  зеленый</span> .

###HTML
```
<form id = "form">

  <input type = "text" placeholder = "Имя">

  <input type = "text" placeholder = "Фамилия">

</form>
```



###JS
```
    let form = document.getElementById("form");

    form.addEventListener("focus", function( ) {

        document.body.style.background = 'red'; }, true);

    form.addEventListener("blur", function(  ) {

         document.body.style.background = 'green';},true);

</script>
```

<img src="/Users/olik/Desktop/2.png" width="60%"/><br>
При событии <span style="color:blue">focus</span>  документ красный
<br><br>
<br>
<img src="/Users/olik/Desktop/1.png" width="60%"/><br>
При событии <span style="color:blue">blur</span> документ зеленый


##Зачем отслеживать потерю фокуса?
##Зачем используют <span style="color:blue">blur</span>?
```В этот момент валидируем введенные данные.```

```Вешать обработчик на форму плохая идея , событие не поймаем,  вариант  ниже```
**не работает,**
``` т.к. событие blur(как и focus) не всплываeт.```

##JS

_<script_ _type_ = _"text/javascript">_

_form.onfocus_ = _function()_ _{_

    document.body.style.background = 'red';
_}_

_form.onblur_ = _function()_ _{_

     document.body.style.background = 'green';
_}_
_</script_>


##Альтернатива <span style="color:blue">blur</span>:  _focusout_.

###Синтаксис

##JS

```
<script type="text/javascript">

   form.addEventListener("focusout", function(  ) {

      document.body.style.background = 'green';},true);

</script>
```




[1]:(../../../Desktop/1.png)(src)
[2]:(../../../Desktop/2.png)(src)
<br><br><br><br><br><br>
```
