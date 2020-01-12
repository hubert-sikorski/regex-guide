![RegEx](img/regex.png)

# Meta signs

* `^` - Beggining of a pattern

```javascript
    const regex = /^he/;

    const correct = ['he', 'hello', 'hell', 'hex', 'hemisphere'];
    const wrong = ['she', 'historic', 'the', 'chef', 'wheel'];
```

* `$` - End of a pattern

```javascript
    const regex = /le$/;

    const correct = ['able', 'sale', 'ankle', 'uncle', 'candle'];
    const wrong = ['lethal', 'clear', 'leave', 'trailer', 'leg'];

    const regex2 = /^.one$/;

    const correct2 = ['done', 'none', 'zone', 'lone', 'tone'];
    const wrong2 = ['loner', 'money', 'phone', 'clone', 'iron'];
```

* `.` - Any single character

```javascript
    const regex = /.an.a/;

    const correct = ['panda', 'fanta', 'manna', 'manga', 'mania'];
    const wrong = ['banana', 'maniac', 'panic', 'sandy', 'dance'];
```

* `[]` - Any of given characters. You can give it a range of characters (i.e. [1-9]) or
specified characters (i.e. [r], [mts], [azdg])

```javascript
    const regex = /[a-z]an[nd]a/;

    const correct = ['panda', 'manna'];
    const wrong = ['fanta', 'manga', 'mania'];

    const regex2 = /[a-z][a-zA-Z0-9.-]/;

    const correct2 = ['pa', 'mA', 'p2', 'x0', 'r.'];
    const wrong2 = ['Ba', '95', '4Z', '.9', 'XX'];
```

* `[^]` - Any character not mentioned in the brackets

```javascript
    const regex = /ban[^se]/;

    const correct = ['bank', 'band', 'bang', 'bani'];
    const wrong = ['bans', 'bane'];
```

* `|` - Any string divided with this mark

```javascript
    const regex = /[gt]o|low|before/;

    const correct = ['go', 'to', 'low', 'before'];
    const wrong = ['plane', 'must', 'hit', 'the', 'steel'];

    const regex2 = /thirteen|13th|13/;

    const correct2 = ['thirteen', '13th', '13'];
    const wrong2 = ['eleven', '12', '14th'];
```

* `()` - Capture group

```javascript
    const regex = /h(a|u)rr(y|i)/;

    const correct = ['harry', 'harri', 'hurry', 'hurri'];
    const wrong = ['harr', 'hrr', 'hurryi', 'ha', 'arry'];

    const regex2 = /(eighth|8th|8)(street|avenue)/;

    const correct2 = ['eighth street', '8th street', 'eighth avenue', '8th avenue', '8 street'];
    const wrong2 = ['8 streets', '9th avenue', 'tenth street', 'one ave', 'street avenue'];
```

* `?` - 0 or 1 element before this mark. Can be placed after parentheses

```javascript
    const regex = /ro?uter/;

    const correct = ['router', 'ruter'];
    const wrong = ['outer', 'roter', 'rter'];

    const regex2 = /(eighth|8(th)?) balls?/;

    const correct2 = ['eighth ball', '8 balls', '8th ball', '8 ball', 'eighth balls'];
    const wrong2 = ['eighth', '8th', 'ball', 'eight balls', '8balls'];
```

* `+` - 1 or more (up to infinite) elements before this mark

```javascript
    const regex = /[0-9]+[abc]/;

    const correct = ['10a', '1b', '4234b', '1408a', '007c'];
    const wrong = ['a', 'c', '14', '12d', '00'];

    const regex2 = /ba(na)+/;

    const correct2 = ['bana', 'banana', 'bananana', 'banananananana'];
    const wrong2 = ['baaaaanana', 'bananas', 'ba', 'bananan', 'banana mammas'];

    const regex3 = /:D+/;

    const correct3 = [':D', ':DD', ':DDDDDDDDDDDD'];
    const wrong3 = [':Dd', ':DDDDdDDdDD', 'XD', ':'];
```

* `*` - 0 or more (up to infinite) elements before this mark

```javascript
    const regex = /[0-9]*[abc]/;

    const correct = ['10a', '1b', '4234b', 'a', 'c'];
    const wrong = ['k', '2335', '14', '12d', '00'];

    const regex2 = /(ba)*(na)*(na)*/;

    const correct2 = ['ba', 'bana', 'banana', 'na', 'nana'];
    const wrong2 = ['banaba', 'ban', 'banannnnn', 'bananan', 'banana mammas'];
```

* `{}` - exact amount of elements before this mark

```javascript
    const regex = /[0-9]{4}/;

    const correct = ['1234', '0000', '8889', '2525', '1999'];
    const wrong = ['12345', '234', '200000', '18', '700'];
```

* `{ ,}` - exact amount or more elements before this mark

```javascript
    const regex = /[ah]{4,}/;

    const correct = ['haha', 'hahahah', 'ahahahah', 'hahahahahahaaa', 'haaaaaa'];
    const wrong = ['haa', 'ha', 'hehe', 'aha', 'hyhy'];
```

* `{ , }` - range specifying amount of elements before this mark

```javascript
    const regex = /d.{2,4}y/;

    const correct = ['duty', 'dizzy', 'daily', 'donkey', 'deploy'];
    const wrong = ['dark', 'display', 'devil', 'dad', 'deployed'];
```
