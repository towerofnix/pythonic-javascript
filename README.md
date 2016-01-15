# Pythonic JavaScript
Todo.. :)

This document assumes you have a perfect browser that generally supports all of ES6. That SHOULD be every browser, as ECMAScript2015/ES6 is the current standard, but for now unfortunately not all browsers implement everything. I personally always use the somewhat glitchy browsers [Google Chrome Canary](https://www.google.com/chrome/browser/canary.html) and [Firefox Nightly](https://nightly.mozilla.org/)/[Developer Edition](https://www.mozilla.org/en-US/firefox/developer/). [Node.js 5](https://nodejs.org/en/blog/release/v5.0.0/) (generally with the `--harmony` flag) is also pretty good with ES6.

Keep in mind that effectively nobody has these browsers [i.e., very few people who will be using your site or program] and you should always use transpilers such as [Babel](https://babeljs.io/) or [Traceur](https://github.com/google/traceur-compiler).

Python version 3.4 is used in the examples, except when otherwise mentioned.

## Control Structures

Note that `for` loops in Python will behave as if they used a `var` statement in JavaScript, so after the loop has exited the final value of the name used in the loop will be accessable, like so:

```python
for item in ['a', 'b', 'c']:
    pass

print item # -> 'c'
```

```javascript
for (var item of ['a', 'b', 'c']);
console.log(item); // -> 'c'
```

However you would normally use `let` instead of `var` in a JavaScript loop statement as `let` helps gets rid of issues such as hoisting.

### Loop through items of a list/array:

```python
for item in [1, 2, 3]:
    pass
```

```javascript
for (let item of [1, 2, 3]);
```

### Loop through keys of a dictionary/object:

```python
for key in {"x": 30, "y": 15}:
    pass
# properties order is reversed in python, wat?
# you can make them go from left to right like this:
# yay for list slicing
for key in list({'x': 30, 'y': 15})[::-1]:
    pass
```

[Read more](http://stackoverflow.com/q/509211/4633828) about Python list slicing!

```javascript
for (let key in {'x': 30, 'y': 15});
// or, replicate the reversed keys thing of Python
// like this:
for (let key of Object.keys({'x': 30, 'y': 15}).reverse());
```

## Array Handling

### Get indexes of a list/array:

```python
range(len(['a', 'b', 'c'])) # [0, 1, 2]
```

```javascript
['a', 'b', 'c'].map((_, i) => item) // [0, 1, 2]
```

### Reverse list/array:

```python
['a', 'b', 'c'][::-1] # [0, 1, 2]
```

```javascript
['a', 'b', 'c'].reverse()
```

## String Handling

### Split string

```python
'hello world'.split(' ') # ['hello', 'world']
```

```javascript
'hello world'.split(' ') // ['hello', 'world']
```

### Join strings

```python
'hello' + ' world' // 'hello world'
```

```javascript
'hello' + ' world' // 'hello world'
// or:
'hello'.concat(' world') // 'hello world'
```

## Convert Types

### Convert to list/array:

```python
list('hello') # ['h', 'e', 'l', 'l', 'o']
```

```javascript
Array.from('hello') // ['h', 'e', 'l', 'l', 'o']
```

### Convert to string:

```python
str(34) # '34'
```

```javascript
(34).toString() // '34'
```

### Convert to number:

Note that Python will raise a ValueError on converting a string literal containing a decimal such as "15.4", while JavaScript will return an integer rounded down (`'15.7'` -> `15`).

```python
int('15') # 15
float('34.75') # 34.75
```

```javascript
parseInt('15') // 15
parseFloat('34.75') // 34.75
```
