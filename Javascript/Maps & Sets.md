# Maps & Sets

## Maps

Maps in JavaScript are key-value pairs where keys can be any data type, not just strings or symbols like in objects. Maps maintain the order of insertion, which means the first key-value pair added to the map will be the first one when iterating.

Example of a Map:

```jsx
let map = new Map();
map.set('name', 'John');
console.log(map.get('name')); // John

```

## WeakMaps

WeakMaps are similar to Maps, but with some key differences. In a WeakMap, keys must be objects and are weakly referenced. This means that if there are no other references to the object, it will be garbage collected. Note that WeakMaps are not iterable.

Example of a WeakMap:

```jsx
let weakmap = new WeakMap();
let obj = {};
weakmap.set(obj, 'John');
console.log(weakmap.get(obj)); // John

```

## Set

A Set in JavaScript is a collection of values. Each value in the Set must be unique. The Set object lets you store unique values of any type, whether primitive values or object references.

Example of a Set:

```jsx
let set = new Set();
set.add(1);
set.add(2);
set.add(3);
console.log(set.has(1)); // true

```

## WeakSet

A WeakSet is a collection of objects. Just like Set, but WeakSet only stores objects and not primitive values. Also, the WeakSet is not iterable and does not have any methods to retrieve the current value.

Example of a WeakSet:

```jsx
let weakset = new WeakSet();
let obj = {};
weakset.add(obj);
console.log(weakset.has(obj)); // true

```