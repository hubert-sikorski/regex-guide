![RegEx](img/regex.png)

# Meta signs

* `^` - Beginning of a pattern

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

    const correct = ['panda', 'fanta', 'manna', 'manga', '5an7a'];
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

    const regex2 = /(eighth|8th|8) (street|avenue)/;

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

* `{}` - Exact amount of elements before this mark

```javascript
    const regex = /[0-9]{4}/;

    const correct = ['1234', '0000', '8889', '2525', '1999'];
    const wrong = ['12345', '234', '200000', '18', '700'];
```

* `{ ,}` - Exact amount or more elements before this mark

```javascript
    const regex = /[ah]{4,}/;

    const correct = ['haha', 'hahahah', 'ahahahah', 'hahahahahahaaa', 'haaaaaa'];
    const wrong = ['haa', 'ha', 'hehe', 'aha', 'hyhy'];
```

* `{ , }` - Range specifying amount of elements before this mark

```javascript
    const regex = /d.{2,4}y/;

    const correct = ['duty', 'dizzy', 'daily', 'donkey', 'deploy'];
    const wrong = ['dark', 'display', 'devil', 'dad', 'deployed'];
```

# Special symbols

If you want to put special symbol inside regular expression you have yo precede
it with `\` sign

* `\.`

```javascript
    const regex = /[0-9]{1-3}\.[0-9]{1-3}\.[0-9]{1-3}\.[0-9]{1-3}/;

    const correct = ['128.0.0.2', '123.456.789.000', '1.1.1.1', '01.01.01.10', '1.23.456.789'];
    const wrong = ['128-0-0-2', '123.1', '1.23.4567.89', '.8.9', '.01.'];
```

* `\*`

```javascript
    const regex = /\*.+/;

    const correct = ['*nothing', '*HAL9000', '*1', '*christmas', '*2999 dollars please'];
    const wrong = ['nothing*', 'nothing', '*nothing*', '*nervous* nancy', '***alert***'];
```

* `\/`

```javascript
    const regex = /^\/\/$/;

    const correct = ['//'];
    const wrong = ['/////', '/headers', '/user/1'];
```

* `\?`

```javascript
    const regex = /^.+\?$/;

    const correct = ['Is this it?', 'Am I correct?', 'Baby?', 'hmm?', 'y?'];
    const wrong = ['?', 'Am I correct', 'I am wrong example', 'Do not copy me', '?Guys?'];
```

* `\:`

```javascript
    const regex = /^.+\:$/;

    const correct = ['Look at these:', 'Question:', '1:'];
    const wrong = [':', ':Question', '::Hey::'];
```

* `\^`

```javascript
    const regex = /.*\^/;

    const correct = ['This is ^', 'Look^', '2^', '^', 'He110    ^'];
    const wrong = ['This is &', '^^^', '^Look^', '2^2', '^ 1'];
```

* `\+`

```javascript
    const regex = /[0-9]+\+[0-9]+/;

    const correct = ['10+11', '999+999', '0+0', '65+35', '1+1000'];
    const wrong = ['333', '22-17', '10 + 11', '0+0 ', '+89'];
```

* `\\`

```javascript
    const regex = /c\:\\ /;

    const correct = ['c:\ '];
    const wrong = ['c:\\', 'c\ ', 'c\:'];
```

* `\=`

```javascript
    const regex = /[0-9]+\+[0-9]+\=[0-9]+/;

    const correct = ['19+20=39', '0+0=0', '4+2=42', '10+10=0', '22222+55555=3186726318762'];
    const wrong = ['19-20=39', '0 + 0 = 0', ' 4+2=42', '10+11' '3+0='];
```

* `\|`

```javascript
    const regex = /x\|\|y/;

    const correct = ['x||y'];
    const wrong = ['x--y', 'x(x||y)', 'x || y'];
```
