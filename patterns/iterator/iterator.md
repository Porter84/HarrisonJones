# Iterator

## Why to use?

- provide a way to access the elements of an aggregate object sequentially without exposing its underlying representation.

## When to use?

- it's a behavioral pattern
- allows to effectively loop over a collection of objects
- these collections may be stored as an array or perhaps something more complex, such as a tree or graph Structure
- you may need to access the items in the collection in a certain order, such as, front to back, back to front, depth first, etc. The Iterator design pattern solves this problem.

## Structure

![iterator uml](https://github.com/Porter84/HarrisonJones/blob/master/patterns/iterator/Iterator_UML_class_diagram.svg "Iterator UML")

_Iterator_
- implements iterator interface with methods first(), next(), etc

_Aggregate_
- items aggregator which creat the iterator for the exact structure

## Typical usage in JavaScript

_jQuery_

```javascript
$.each( ['john', 'dave', 'rick', 'julian'], function (index, value) {
  console.log(index + ': ' + value);
});
 
$('li').each( function (index) {
  console.log(index + ': ' + $(this).text());
});
```

_AngularJS_

```javascript
let obj = {name: 'misko', gender: 'male'};
angular.forEach(obj, function(value, key) {
  console.log(key + ': ' + value);
});
```