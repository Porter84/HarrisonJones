# Composite

## Why to use?
- it is a structural pattern
- dealing with Tree-structured data makes code more complex, and therefore, error prone. The solution is an interface that allows treating complex and primitive objects uniformly.
- compose objects into tree structures, which represent part-whole hierarchies
- each item in the collection can hold other collections themselves, creating deeply nested structures

## When to use?

- Composite should be used when you can ignore the difference between compositions of objects and individual objects.

## Structure

![composite uml](https://github.com/Porter84/HarrisonJones/blob/master/patterns/composite/Composite_UML_class_diagram.png "Composite UML")

_Component_
- is the abstraction for all components, including composite ones
- declares the interface for objects in the composition

_Leaf_
- represents leaf objects in the composition
- implements all Component methods

_Composite_
- represents a composite Component (component having children)
- implements methods to manipulate children
- implements all Component methods, generally by delegating them to its children

## Typical usage in JavaScript

In jQuery, when we're applying methods to an element or collection of elements

```javascript
// Single elements
$('#singleItem').addClass('active');
$('#container').addClass('active');
 
// Collections of elements
$('div').addClass('active');
$('.item').addClass('active');
$('input').addClass('active');
```