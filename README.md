# Pythonic JavaScript
Todo.. :)

This document assumes you have a perfect browser that generally supports all of ES6. That SHOULD be every browser, as ECMAScript2015/ES6 is the current standard, but for now unfortunately not all browsers implement everything. I personally always use the somewhat glitchy browsers [Google Chrome Canary](https://www.google.com/chrome/browser/canary.html) and [Firefox Nightly](https://nightly.mozilla.org/)/[Developer Edition](https://www.mozilla.org/en-US/firefox/developer/). [Node.js 5](https://nodejs.org/en/blog/release/v5.0.0/) is also pretty good with ES6, and you can always use transpilers such as [Babel](https://babeljs.io/) or [Traceur](https://github.com/google/traceur-compiler).

## Loops

**Loop through items of a list/array:**

```python
for item in [1, 2, 3]:
    pass
```

```javascript
for (var item of [1, 2, 3]) {
  // ...
};
```

**Loop through keys of a dictionary/object:**

```python
for key in {"x": 30, "y": 15}:
    pass
# properties order is reversed in python, wat?
# you can make them go from left to right like this:
keys = list({"x": 30, "y": 15})
keys.reverse()
for key in keys:
    pass
```

```javascript
for (var key in {"x": 30, "y": 15}) {
  // ...
}
// or, replicate the reversed keys thing of Python
// like this:
for (var key of Object.keys({"x": 30, "y": 15}).reverse()) {
  // ...
}
```

**Get indexes of a list/array:**

```python
range(len(['a', 'b', 'c'])) # [0, 1, 2]
```

```javascript
['a', 'b', 'c'].map((_, i) => item) // [0, 1, 2]
```
