# Templates

In Ractive, templates (until they get [parsed](ractive-parse.md), at least) are just snippets of HTML, with a few differences. A template should be *well-formed* - Ractive's parser is not quite as forgiving as the HTML parsers found in browsers (though it does allow things like implicitly closed elements).

Strictly speaking, a Ractive template is not valid HTML (for one thing, 'valid HTML' describes an entire document, and we're only dealing with snippets), but *it doesn't matter*, even if you're the kind of obsessive who can't stand a single error in the [W3C validator](http://validator.w3.org/), because it all comes out as lovely standards-compliant DOM.

For reference, however, the differences between Ractive templates and HTML are listed on this page.

## Mustaches

The most obvious difference is that Ractive templates contain [mustaches](mustaches.md) to facilitate data binding.

## Event directives

Elements in a Ractive template can have [events](method calls.md), which look like attributes but don't get rendered to the DOM as attributes (they are intercepted, and used as event binding instructions instead):

```html
<button on-click='@this.activate()'>Activate!</button>
```

## Transitions

Another item in the set of things-that-look-like-attributes-but-aren't, [transitions](transitions.md) allow you to specify how elements should behave when they first get introduced to the DOM and when they get removed from it later:

```html
<div fade-in>This element will fade in gradually when it renders</div>
```

## Decorators

[Decorators](Decorators.md) can decorate elements as they are rendered to the DOM. These also look like attributes, but they never get added to the DOM themselves.

```html
<div as-ace-editor>This element will be turned into an Ace Editor.</div>
```