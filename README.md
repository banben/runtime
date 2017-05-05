# d3-express

…

## Installing

If you use NPM, `npm install d3-express`. Otherwise, download the [latest release](https://github.com/d3/d3-express/releases/latest). You can also load directly from [unpkg.com](https://unpkg.com/d3-express/). AMD, CommonJS, and vanilla environments are supported. In vanilla, a `d3` global is exported:

```html
<script src="https://unpkg.com/d3-express@0"></script>
<script>

var runtime = d3.runtime();

</script>
```

## API Reference

### Runtime

<a href="#runtime" name="runtime">#</a> d3.<b>runtime</b>([<i>builtins</i>])

Returns a new reactive [runtime](#runtime). If a *builtins* object is specified, each property on the *builtins* object defines a builtin variable for the runtime; these builtin variables are available as named inputs to any [defined variables](#variable_define) on any [module](#modules) associated with this runtime. For example, to define the builtin `color`:

```js
var module = d3.runtime({color: "red"}).module();

module.variable().define(null, ["color"], color => {
  console.log(`Hello, ${color}.`); // "Hello, red."
});
```

Defined variables may not override builtins. If *builtins* is not specified, the d3.express [standard library](#standard-library) is used.

<a href="#runtime_module" name="runtime_module">#</a> <i>runtime</i>.<b>module</b>()

Returns a new [module]

### Module

<a href="#module_variable" name="module_variable">#</a> <i>module</i>.<b>variable</b>([<i>element</i>])

…

### Variable

<a href="#variable_define" name="variable_define">#</a> <i>variable</i>.<b>define</b>(<i>name</i>, <i>inputs</i>, <i>definition</i>)

…

<a href="#variable_delete" name="variable_delete">#</a> <i>variable</i>.<b>delete</b>()

…

<a href="#variable_import" name="variable_import">#</a> <i>variable</i>.<b>import</b>(<i>module</i>, <i>imports</i>)

…

## Standard Library

By default, [d3.runtime](#runtime) provides the following standard builtins:

* [DOM](#dom) - create HTML and SVG elements.
* [Files](#files) - read local files into memory.
* [Generators](#generators) - utilities for generators and iterators.
* [Promises](#promises) - utilities for promises.
* [require](#require) - load third-party libraries.

### DOM

<a href="#DOM_canvas" name="DOM_canvas">#</a> DOM.<b>canvas</b>(<i>width</i>, <i>height</i>)

…

```js
DOM.canvas(960, 500)
```

<a href="#DOM_element" name="DOM_element">#</a> DOM.<b>element</b>([<i>uri</i>, ]<i>name</i>[, <i>options</i>])

…

```js
DOM.element("h1")
```

<a href="#DOM_html" name="DOM_html">#</a> DOM.<b>html</b>(<i>strings</i>)

…

```js
DOM.html`<h1>Hello, world!</h1>`
```

<a href="#DOM_input" name="DOM_input">#</a> DOM.<b>input</b>(<i>type</i>)

…

```js
DOM.input("file")
```

<a href="#DOM_pre" name="DOM_pre">#</a> DOM.<b>pre</b>(<i>strings</i>)

…

```js
DOM.pre`This is pre-formatted text.`
```

<a href="#DOM_range" name="DOM_range">#</a> DOM.<b>range</b>([<i>min</i>, ]<i>max</i>[, <i>step</i>])

…

```js
DOM.range(-180, 180, 1)
```

<a href="#DOM_select" name="DOM_select">#</a> DOM.<b>select</b>(<i>values</i>)

…

```js
DOM.select(["red", "green", "blue"])
```

<a href="#DOM_svg" name="DOM_svg">#</a> DOM.<b>svg</b>(<i>width</i>, <i>height</i>)

…

```js
DOM.svg(960, 500)
```

<a href="#DOM_text" name="DOM_text">#</a> DOM.<b>text</b>(<i>string</i>)

…

```js
DOM.text("Hello, world!")
```

### Files

<a href="#Files_buffer" name="Files_buffer">#</a> Files.<b>buffer</b>(<i>file</i>)

…

<a href="#Files_text" name="Files_text">#</a> Files.<b>text</b>(<i>file</i>)

…

<a href="#Files_url" name="Files_url">#</a> Files.<b>url</b>(<i>file</i>)

…

### Generators

<a href="#Generators_filter" name="Generators_filter">#</a> Generators.<b>filter</b>(<i>iterator</i>, <i>test</i>)

…

<a href="#Generators_input" name="Generators_input">#</a> Generators.<b>input</b>(<i>input</i>)

…

<a href="#Generators_map" name="Generators_map">#</a> Generators.<b>map</b>(<i>iterator</i>, <i>transform</i>)

…

<a href="#Generators_range" name="Generators_range">#</a> Generators.<b>range</b>([<i>start</i>, ]<i>stop</i>[, <i>step</i>])

…

<a href="#Generators_valueAt" name="Generators_valueAt">#</a> Generators.<b>valueAt</b>(<i>iterator</i>, <i>index</i>)

…

### Promises

<a href="#Promises_delay" name="Promises_delay">#</a> Promises.<b>delay</b>(<i>duration</i>[, <i>value</i>])

…

<a href="#Promises_when" name="Promises_when">#</a> Promises.<b>when</b>(<i>date</i>[, <i>value</i>])

…

### require

<a href="#require" name="require">#</a> <b>require</b>(<i>name</i>)

…
