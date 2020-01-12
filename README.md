![RegEx](img/regex.png)

# Meta signs

* `^` - Beggining of a pattern

```javascript
    const regex = /^he/;

    const correct = [he, hello, hell, hex, hemisphere];
    const wrong = [she, historic, the, chef, wheel];
```

* `$` - End of a pattern

```javascript
    const regex = /le$/;

    const correct = [able, sale, ankle, uncle, candle];
    const wrong = [lethal, clear, leave, trailer, leg];

    const regex2 = /^.one$/;

    const correct2 = [done, none, zone, lone, tone];
    const wrong2 = [loner, money, phone, clone, iron];
```

* `.` - Any single character

```javascript
    const regex = /.an.a/;

    const correct = [panda, fanta, manna, manga, mania];
    const wrong = [banana, maniac, panic, sandy, dance];
```
