node-range
==========

Simple Lazy Ranges for Node/Javascript

## Install:

```
npm install node-range
```

## Usage:

```js
/*
  Faster than Array.map since it does
  array composition and function application in same step
*/
var arr = range(1,11).map(function(i) {
    return i*5
})
console.log(arr)

/*
You can still do
*/
arr = range(1,11).toArray().map(function(i) {
    return i*2
})
console.log(arr)


/*
As well we can just execute a function against a range but not return an array
*/
range(1,11).forEach(function(i) {
    console.log(Math.exp(i,2))
})

/*
As well we can execute Async
*/
range(1,11).forEachAsync(function(i) {
    console.log('num:' + Math.exp(i,2));
})
console.log('This should come first')
```

### Inclusive vs Exclusive

`range(a, b)` will default to calculating the "exclusive" range, that is every number up to but not including the last:

```js
range(1, 5).forEach(function(i) {
  console.log(i);
});
// outputs:
//   1234
```

To set it to be "inclusive", which will include the last number, pass `true` as a third argument:

```js
range(1, 5, true).forEach(function(i) {
  console.log(i);
});
// outputs:
//   12345
```

