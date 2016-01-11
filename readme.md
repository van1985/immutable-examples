# Immutable
> This project is an application skeleton for a React with Redux app.

`React` is a UI library developed at Facebook to facilitate the creation of interactive, stateful & reusable UI components. It is used at Facebook in production, and Instagram.com is written entirely in React.

## Why do we need immutable?

###Objects & Arrays are mutable

JavaScript arrays & objects are mutable data. If you create an object, reference it as a different variable, and modify it, both references point to a changed value.

```javascript
var myself = { name: 'Tom' };
var someoneElse = myself;
myself.name = 'Thomas';
// both myself & someoneElse are now equal to { name: 'Thomas' }
```

Mutability applies to arrays too: common array operations like .sort(), .push(), and .pop() all change arrays in place.

```javascript
var numbers = [3, 2, 1];
var sorted = numbers.sort();
// both numbers & sorted are equal to [1, 2, 3]
// because calling .sort() sorts the array in-place
```

###Immutable.js

Luckily, the Immutable.js makes immutable data simple, by providing custom and efficient datastructures for unchanging data.

```javascript
var myself = Immutable.Map({ name: 'Tom' });
```

Instead of changing myself in-place like I would with vanilla JavaScript, Immutable provides methods that yield new modified objects.

```javascript
var someoneElse = myself.set('name', 'Thomas');
```

If you've dealt with this problem before, you might notice that there's another way of approaching this problem, by cloning objects:

```javascript
var myself = { name: 'Tom' };
// clone myself, to ensure that changing someoneElse doesn't
// mutate it.
var someoneElse = JSON.parse(JSON.stringify(myself));
myself.name = 'Thomas';
```

Immutable improves upon this hack with a guarantee and an optimization:

* Immutable's methods like .set() can be more efficient than cloning because they let the new object reference data in the old object: only the changed properties differ. This way you can save memory and performance versus constantly deep-cloning everything.
* It's nearly impossible to accidentally mutate an Immutable object, and remarkably easy to accidentally forget to clone a normal object. Immutable objects give a strong guarantee that nowhere does anyone mutate data in-place.

## Immutable.js data structures

Immutable.js has the following data structures:

* List,
* Stack,
* Map,
* OrderedMap,
* Set,
* OrderedSet,
* Record,
* lazy Seq.

## Usage

### Installation

```
$ sudo npm install
```

### Run App

Open <b> index.html </b>file in any browser
