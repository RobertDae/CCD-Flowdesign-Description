Integration is about the flow of data between functional units, it's about the arrows in flow designs:

![](images/implementing_integration/genericintegration.png)

There are many ways the connections between functional units can be implemented. But unless functional units are distributed across threads or processes or even machines it all boils down to simple functional calls.

The integration itself is just another functional unit. Its outer form thus is implemented by following the input/output *port* translation patterns, e.g.

```
Z i(X x) {
  ...;
  return z;
}
```

### Integrating Single Outputs
Internally this function needs to "wire-up" the functions for the functional units to integrate. As long as those function just produce single non-stream output that is simple, e.g.

```
Z i(X x) {
  var y = f(x);
  var z = g(y);
  return z;
}
```

Each input *port* function is called and its result is passed to the next input *port* function.

### Integrating Multiple Outputs
With multiple output the integration depends on the implementation (and sematics) of the *ports*:

![](images/implementing_integration/integrateseveraloutputs.png)

In this example the output *ports* are meant to carry data in a mutually exclusive manner: either a `y` is produced or an `s`:

```
Y f(X x, Action<Y> onY, Action<S> onS) {
  ...
}

Z g(Y y) { ... }

Z h(S s) { ... }

Z i(X x) {
  Z z;
  f(x,
    y => z = g(y),
    s => z = h(s));
  return z;
}
```

Notice how the continuations are passed in as lambda expressions.

///// out params

### Integrating Stream Output