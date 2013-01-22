Набор необходимых скриптов и прочего для типовой верстки

В репозитории находится типовой шаблон для верстки

##Структура файлов

```
- css
  - bootstrap-modal.css
- js
  - bootstrap-modal.js
  - jquery-1.9.0.min.js
- index.html
```


#Bootstrap Modal
Модальное окно с поддержкой методов и событий

##HTML

```
<div id="myModal" class="modal hide fade" tabindex="-1" role="dialog" aria-hidden="true">
  <div class="modal-header">
    <button type="button" class="close" data-dismiss="modal" aria-hidden="true">×</button>
    <h4>Изменить группу</h4>
  </div>
  <div class="modal-body" style="overflow: visible;"> 

  </div>
  <div class="modal-footer">
      <button class="btn btn-small btn-primary">Сохранить</button>
      <button class="btn btn-small" data-dismiss="modal" aria-hidden="true">Отмена</button>
  </div>
</div>
```


##Использование без непосредственного вызова

Сперва подключить JavaScript. В контрольный элемент пропишисать `data-toggle="modal"`, прописать ссылку на вызываемое окно `data-target="#foo"` или `href="#foo"`.
```
<button type="button" data-toggle="modal" data-target="#myModal">Launch modal</button>
```
или
```
<a href="#myModal" role="button" data-toggle="modal">Вызвать модальное окно</a>
```

##Использование с вызовом через метод

```
$('#myModal').modal(options)
```

Опции (options) можно, так же, прописать непосредственно в теге активного компонента в атрибуте с префиксом `data-`, например `data-backdrop=""`


##ОПЦИИ

```
Имя         Тип        По умолчанию    Описание
backdrop    boolean    true            Включает фон элемента. Кроме того, укажите `static`, что бы не закрывать модальное окно при щелчке по фону.
keyboard    boolean    true            Закрывает модальное окно при нажатии клавиши `escape`.
show        boolean    true            Показывает модальное окно при инициализации
remote      path       false           Если удаленный контент будет загружен через jQuery метод load и помещен в тело .modal. Если вы используете api данных, в качестве альтернативы вы можете использовать href тега для указания удаленного источника. Пример этого показан ниже:
```
``<a data-toggle="modal" href="remote.html" data-target="#modal">click me</a>``



##МЕТОДЫ

Активирует модального окна
`.modal(options)`
```
$('#myModal').modal({
  keyboard: false
})
```

Ручной переключение модального окна
`.modal('toggle')`
```
$('#myModal').modal('toggle')
```

Ручной запуск модального окна
`.modal('show')`
```
$('#myModal').modal('show')
```

Ручное скрытие модального окна
`.modal('hide')`
```
$('#myModal').modal('hide')
```



##СОБЫТИЯ

```
Событие     Описание
show        This event fires immediately when the show instance method is called.
shown       This event is fired when the modal has been made visible to the user (will wait for css transitions to complete).
hide        This event is fired immediately when the hide instance method has been called.
hidden      This event is fired when the modal has finished being hidden from the user (will wait for css transitions to complete).
```
```
$('#myModal').on('hidden', function () {
  // do something…
})
```
