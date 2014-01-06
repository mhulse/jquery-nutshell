# Nutshell

<a href="http://gruntjs.com/" title="Built with Grunt"><img src="https://cdn.gruntjs.com/builtwith.png" alt="Built with Grunt" align="right"></a>

**In a nutshell, simple jQuery-powered tabs.**

---

## Demo

[![qr code](http://chart.apis.google.com/chart?cht=qr&chl=https://github.com/mhulse/jquery-nutshell/&chs=240x240)](http://mhulse.github.com/jquery-nutshell/demo/)

**Source:** [jquery.nutshell.js](https://raw.github.com/mhulse/jquery-nutshell/gh-pages/nutshell/jquery.nutshell.js) | [jquery.nutshell.min.js](https://raw.github.com/mhulse/jquery-nutshell/gh-pages/nutshell/jquery.nutshell.min.js)

## Installation

There are several ways to install this code:

1. Download as a [`zip`](https://github.com/mhulse/jquery-nutshell/archive/gh-pages.zip).
1. Clone it: `$ git clone https://github.com/mhulse/jquery-nutshell.git`.
1. Fork it and clone: `$ git clone git@github.com:USERNAME/jquery-nutshell.git`.
1. Just grab the relevant [JS](https://raw.github.com/mhulse/jquery-nutshell/gh-pages/nutshell/jquery.nutshell.js) ([uglified](https://raw.github.com/mhulse/jquery-nutshell/gh-pages/nutshell/jquery.nutshell.min.js)) files.
1. Using [Bower](http://bower.io/): `$ bower install https://github.com/mhulse/jquery-nutshell.git`.

## Usage

Setting up Nutshell is simple ...

### Markup:

Here's the basic HTML:

```html
<ul class="nutshell">
	<li><a href="#foo">Foo</a></li>
	<li><a href="#bar">Bar</a></li>
	<li><a href="#baz">Baz</a></li>
</ul>

<div id="foo">...</div>

<div id="bar">...</div>

<div id="baz">...</div>
```

### Styling:

These tabs can be styled as you see fit. Check out the [demo page](http://mhulse.github.com/jquery-nutshell/demo/) for a complete working example.

### Javascript:

Put [jQuery](http://jquery.com/) on your page:

```html
<script src="//ajax.googleapis.com/ajax/libs/jquery/1.10.2/jquery.min.js"></script>
```

... and link to the plugin:

```html
<script src="jquery.nutshell.min.js"></script>
```

Next, Nutshell can be instantiated like so:

```html
<script>
	
	$(document).ready(function() {
		
		$('.nutshell').nutshell();
		
	});
	
</script>
```

Here's an example with all the options:

```html
<script>
	
	$(document).ready(function() {
		
		var console = (window.console || { log : function() {} });
		
		$('.nutshell').nutshell({
			
			classSelected : 'nutshell-selected',
			classSingle   : 'nutshell-single',
			animIn        : { opacity: 'show' },
			animOut       : { opacity: 'hide' },
			easeIn        : 'swing',
			easeOut       : 'swing',
			speedIn       : 'fast',
			speedOut      : 'fast',
			onInit        : function() { console.log('onInit', this) },
			onAfterInit   : function() { console.log('onAfterInit', this) },
			onBeforeShow  : function($active, $inactive, $panel) { console.log('onBeforeShow', this, $active, $inactive, $panel) },
			onShow        : function($active, $inactive, $panel) { console.log('onShow', this, $active, $inactive, $panel) },
			onBeforeHide  : function($active, $inactive, $panel) { console.log('onBeforeHide', this, $active, $inactive, $panel) },
			onHide        : function($active, $inactive, $panel) { console.log('onHide', this, $active, $inactive, $panel) }
			
		});
		
		//$('.nutshell').nutshell('destroy');
		
	});
	
</script>
```

… where:

Option | Description | Default
:-- | :-- | :--
`classSelected` | Selected tab CSS class. | `nutshell-selected`
`classSingle | Have "external" link(s) open a single tab based on its hash? | `''`
`animIn` |  What animation object to use to show the panels. | `{ opacity: 'show' }`
`animOut` | IBID, but for hiding. | `{ opacity: 'hide' }`
`easeIn` | Easing function in. | `'swing'`
`easeOut` | Easing function out. | `'swing'`
`speedIn` | Animation speed in. | `'normal'`
`speedOut` | Animation speed out. | `'normal'`
`onInit` | Callback on plugin initialization. | `$.noop`
`onAfterInit` | Callback after plugin initialization. | `$.noop`
`onBeforeShow` | Before reveal animation begins. | `$.noop`
`onShow` | After reveal animation ends. | `$.noop`
`onBeforeHide` | Before hide animation begins. | `$.noop`
`onHide` | After hide animation ends. | `$.noop`

### Advanced:

1. All options can be overidden via an [HTML5 data attribute](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Using_data_attributes) named `data-ion-options`; the value of this attribute **must** be valid [JSON](http://json.org/) syntax.

 For example:

 ```html
 <ul class="nutshell" data-nutshell-options='{ "classSelected" : "foo" }'>
 	...
 </ul>
 ```

 **Note** the nesting order of the single (`'`) and double (`"`) quotes.

1. The tabs can be triggered via external clicks (e.g., page navigation).

 To enable this featue, set a class name for the `classSingle` option:

 ```js
 classSingle : 'nutshell-single',
 ```

 ... and add the `classSingle` class to any link; the `href` value should target the desired tab panel ID:

 ```html
 <a class="nutshell-single" href="#foo">FOO</a>
 ```

1. The accordion can be triggered via external clicks (e.g., page navigation).

1. Accordion panels can be opened via URI hash, like so:

 [http://mhulse.github.io/jquery-nutshell/demo/#bar](http://mhulse.github.io/jquery-nutshell/demo/#bar)

## Contributing

Please read the [CONTRIBUTING.md](https://github.com/mhulse/jquery-nutshell/blob/gh-pages/CONTRIBUTING.md).

## Feedback

[Bugs? Constructive feedback? Questions?](https://github.com/mhulse/jquery-nutshell/issues/new?title=Your%20code%20sucks!&body=Here%27s%20why%3A%20)

## Changelog

* [v1.0.0 milestones](https://github.com/mhulse/jquery-nutshell/issues?direction=desc&milestone=1&page=1&sort=updated&state=open)

## [Release history](https://github.com/mhulse/jquery-nutshell/releases)

* 2013-12-26   [v1.0.0](https://github.com/mhulse/jquery-nutshell/releases/tag/v1.0.0)   Go time!

---

#### LEGAL

Copyright &copy; 2013 [Micky Hulse](http://mky.io)

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this work except in compliance with the License. You may obtain a copy of the License in the LICENSE file, or at:

[http://www.apache.org/licenses/LICENSE-2.0](http://www.apache.org/licenses/LICENSE-2.0)

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.

<img width="20" height="20" align="absmiddle" src="https://github.global.ssl.fastly.net/images/icons/emoji/octocat.png" alt=":octocat:" title=":octocat:" class="emoji">
