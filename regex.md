# Regex notes with js examples

### m - multiline search
```
const str = "1 cat \n2 cat\n3 cat"
console.log(str.match(/^\d/gm)) // [ '1', '2', '3' ]
```
### note that regexp.test(str) instead of str.test()!
```
console.log(/love/.test("I like you")) // true
console.log(/love/.test("I love you")) // false 
```
### ^ - start, $ - end
```
console.log(/^\d/.test("22")) // true, start with digit
console.log(/\d$/.test("adaa22")) // true, end with digit
console.log(/^\d$/.test("22")) // true, start and end with digit
console.log(/^\d$/.test("22a")) // false, start and end with digit
```
### \b - is contains as separate word
```
console.log(/\bJava\b/.test("Java!")) // true
console.log(/\bJava\b/.test("JavaScript")) // false 
```
### find or avoid special symbols 
```
[ \ ^ $ ( ) . | ? * + / - list of special symbols in regex
console.log(/\^\$/.test("^$")) // true
const reg = new RegExp("\\^\\$") // use \\ instead \
```
### Quantifiers
- \* = {0,} - zero or more
- \+ = {1,} - one or more 
- ? = {0,1} - zero or one
- {n} - n is number 1,2,3...
- {n,} - >= n
- {x,y} - between x and y match inclusive
```
console.log(/\d{3,}/.test("1234")) // true
console.log(/\d{3,}/.test("12")) // false 
```
### ? magick
```
console.log(`I "love" or "like" you`.match(/".+"/g)) // [`"love" or "like"`]
console.log(`I "love" or "like" you`.match(/".+?"/g)) // [`"love"', `"like"`]
```
### Catching with ()
```
console.log("I love you".match(/(lo)ve/)[0]) // love 
console.log("I love you".match(/(lo)ve/)[1]) // lo
console.log("Joe Biden".replace(/(\w+) (\w+)/, "$2 $1")) // Biden Joe

```
