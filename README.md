async
====

  A place to put together clean and simple asynchronous patterns for nodejs and your browser.

## Emitter

  > observer

  **[emitter](http://github.com/component/component)** is a module made by the team [component](http://github.com/component). 

```js
var emitter = new Emitter();
emitter.on('changed', function() {
	// do something on changed
});
emitter.emit('changed');
```

<!--   Emitter is from far the module I use the most. It is clean, simple, can be used on nodejs instead [EventEmitter](http://nodejs.org/api/events.html)  -->
<!-- 
  Here's some projects related: -->


## Promises

  > promise

  **[promise](http://github.com/bredele/promise)** is a promise A+ [implementation](http://promises-aplus.github.io/promises-spec/).

```js
var promise = new Promise();
promise.then(function(value) {
	
});
promise.resolve('because');
```

## Mood

  > finite state machine

  **[mood](https://github.com/bredele/mood)** is a finite state machine based on [emitter](http://github.com/component/emitter). It allows you to define transitions from one state to an other.

```js
var states = new Mood('open');

// transition open to locked
states.add('open','lock', function() {
  //do something
}, 'locked');

states.emit('lock');
```

## Queue

  > asynchronous emitter

  **[queue](http://github.com/bredele/emitter-queue)** is a plugin for [emitter](http://github.com/component/emitter) and **[datastore](http://github.com/bredele/datastore)** that allows to listen events even after they have been fired.

```js
var emitter = new Emitter();
Queue(emitter);

emitter.queue('changed');
emitter.on('changed', function() {
	// do something on changed
});
```

## Door

  > door pattern

  **[door](https://github.com/bredele/doors)** is a design pattern I invented. 


```js
var door = new Door('awesome');
door.lock('foo');
door.lock('bar');

door.on('open', function() {
	// do something when every lock are unlocked
});

door.unlock('bar', 'foo');
```

  A door has two states (opened and closed) and can switch from one to an other indefinitely. Doors is the opposite of a finite state machine, a transition is trigerred by one or several conditions (or locks). To be opened, a door needs to unlock all locks and one lock is enough to close the door.

<!--   dire pourquoi c'est bien  -->
