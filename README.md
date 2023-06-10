### Здесь я писал логику своих собственных объектов на JS

Реализовал набор функций, для работы со словарём, построенным на хеш-таблице, без разрешения коллизий.

По сути просто реализовал объекты. Представил что в языке объектов нет и мы их хотим добавить.

- **make()** — создаёт новый пустой словарь и возвращает его
```js 
const map = make();
console.log(map); // []
```
- **set(map, key, value)** — устанавливает в словарь значение по ключу. Работает и для создания и для изменения. Функция возвращает true, если удалось установить значение. При возникновении коллизии, функция никак не меняет словарь и возвращает false
```js
const map = make();
set(map, 'key1', 'value1');
console.log(map); // [ <496 empty items>, [ 'key1', 'value1' ] ]
```
- **get(map, key, defaultValue = null)** — возвращает значение указанного ключа. Параметр defaultValue — значение, которое функция возвращает, если в словаре нет ключа (по умолчанию равно null). При возникновении коллизии функция также возвращает значение по умолчанию
Функции set() и get() принимают первым параметром словарь. Передача идёт по ссылке, поэтому set() может изменить его напрямую.

```js
const map = make();
set(map, 'key2', 'value2');
result = get(map, 'key2');
console.log(result); // => "value2"
```