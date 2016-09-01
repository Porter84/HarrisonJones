# Adapter

## Why to use?

- An adapter helps two incompatible interfaces to work together.

## When to use?

- Interfaces may be incompatible but the inner functionality should suit the need.
- The Adapter design pattern allows otherwise incompatible classes to work together by converting the interface of one class into an interface expected by the clients.

## Structure

There are two types of adapter patterns:

### Object adapter pattern

In this type of adapter pattern, the adapter contains an instance of the class it wraps.

![adapter uml](https://github.com/Porter84/HarrisonJones/blob/master/patterns/adapter/Adapter_UML_class_diagram_1.png "Adapter UML")

### Class adapter pattern

This type of adapter uses multiple polymorphic interfaces implementing or inheriting both the interface that is expected and the interface that is pre-existing.

![adapter uml](https://github.com/Porter84/HarrisonJones/blob/master/patterns/adapter/Adapter_UML_class_diagram_2.png "Adapter UML")

## Typical usage in JavaScript

```JavaScript
// Cross browser opacity:
// opacity: 0.9; Chrome 4+, FF2+, Saf3.1+, Opera 9+, IE9, iOS 3.2+, Android 2.1+
// filter: alpha(opacity=90); IE6-IE8
 
// Setting opacity
$( ".container" ).css( { opacity: .5 } );
 
// Getting opacity
var currentOpacity = $( ".container" ).css('opacity');
```