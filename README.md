@kollorg/illum-magni
----

A small library for using and manipulating key paths in JavaScript.

# Installation

````bash
npm install --save @kollorg/illum-magni
````

````javascript
const @kollorg/illum-magni = require('@kollorg/illum-magni');
````
    
# Getting / Setting Values

## Getting Values

````javascript
@kollorg/illum-magni(obj).get('my.keypath');
````

### Getting values in array and sub-arrays.

````javascript
@kollorg/illum-magni(obj).get.all('my.keypath');
````

## Setting Values

````javascript
@kollorg/illum-magni(obj).set('my.keypath', value);
````

# Manipulating Key Paths

## Components

````javascript
const components = @kollorg/illum-magni.components('my.key.path');
/* -> ['my','key','path'] */
````

> Throws an error if input is not a string.

## Joining

````javascript
const keyPath = @kollorg/illum-magni.join(['my','key','path']);
/* -> 'my.key.path' */
````

> Throws an error if input is not an array.

## Appending Keys

````javascript
const keyPath = @kollorg/illum-magni.append('my.key', 'path');
/* -> 'my.key.path' */
````

or

````javascript
const keyPath = @kollorg/illum-magni.append('my', ['key', 'path']);
/* -> 'my.key.path' */
````

> Both inputs can be either strings or arrays.

## Last

### Getting

````javascript
const lastComponent = @kollorg/illum-magni.last('my.key.path');
/* -> 'path' */
````

> Input can be a string or an array.

### Removing

````javascript
const keyPath = @kollorg/illum-magni.eatLast('my.key.path');
/* -> 'my.key' */
````

> Input can be a string or an array.

## First

### Getting

````javascript
const firstComponent = @kollorg/illum-magni.first('my.key.path');
/* -> 'my' */
````

> Input can be a string or an array.

### Removing

````javascript
const keyPath = @kollorg/illum-magni.eatFirst('my.key.path');
/* -> 'key.path' */
````

or

````javascript
const keyPath = @kollorg/illum-magni.eatFirst('my.key.path', 'my.key');
/* -> 'path' */
````

> Input can be a string or an array.

> Latter example with throw an error if second key path is not within the first.

## Match

````javascript
const within = @kollorg/illum-magni.within('my.key.path', 'my.key');
/* -> true */
````

````javascript
const is = @kollorg/illum-magni.is('my.key.path', 'my.key');
/* -> false */
````

> Both inputs can be either strings or arrays.

# Options

All methods supports options, which is provided as an object as the last parameter.

The table below shows the supported key(s).

| Name | Default value | Description | 
|:-----|:--------------|:------------|
| `separator` | `.` | A string that represents the separation characters of keys in a key path string.

# License

MIT (see LICENSE).
