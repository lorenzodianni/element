<p align="center"><img src="http://element-project.io/img/Element-Project.png" width="500" alt="Element Project"></p>

#

[![Code Climate](https://codeclimate.com/github/lorenzodianni/element-project/badges/gpa.svg)](https://codeclimate.com/github/lorenzodianni/element-project)
[![Build Status](https://travis-ci.org/lorenzodianni/element-project.svg?branch=master)](https://travis-ci.org/lorenzodianni/element-project)
[![codecov](https://codecov.io/gh/lorenzodianni/element-project/branch/master/graph/badge.svg)](https://codecov.io/gh/lorenzodianni/element-project)

* [El](#El) : <code>object</code>
    * [.appendChild(element, child)](#El.appendChild) ⇒ <code>HTMLElement</code>
    * [.appendChildren(element, children)](#El.appendChildren) ⇒ <code>HTMLElement</code>
    * [.create(selector)](#El.create) ⇒ <code>HTMLElement</code>
    * [.setAttribute(element, attrs)](#El.setAttribute) ⇒ <code>HTMLElement</code>
    * [.style(element, styles)](#El.style) ⇒ <code>HTMLElement</code>
    * [.innerHTML(element, html)](#El.innerHTML) ⇒ <code>HTMLElement</code>
    * [.innerText(element, text)](#El.innerText) ⇒ <code>HTMLElement</code>
    * [.generate(selector, options)](#El.generate) ⇒ <code>HTMLElement</code>
    * [.get(selector)](#El.get) ⇒ <code>HTMLElement</code>
    * [.getAll(selector)](#El.getAll) ⇒ <code>NodeList</code>
    * [.insertAdjacentHTML(element, position, html)](#El.insertAdjacentHTML) ⇒ <code>HTMLElement</code>

<a name="El.appendChild"></a>

### El.appendChild(element, child) ⇒ <code>HTMLElement</code>
**Kind**: static method of <code>[El](#El)</code>  

| Param | Type |
| --- | --- |
| element | <code>HTMLElement</code> | 
| child | <code>HTMLElement</code> | 

**Example**  
```js
El.appendChild(El.get('.foo'), El.create('.bar'));

// <div class="foo">
//   <div class="bar"></div>
// </div>
```
<a name="El.appendChildren"></a>

### El.appendChildren(element, children) ⇒ <code>HTMLElement</code>
**Kind**: static method of <code>[El](#El)</code>  

| Param | Type |
| --- | --- |
| element | <code>HTMLElement</code> | 
| children | <code>Array.&lt;HTMLElement&gt;</code> | 

**Example**  
```js
El.appendChildren(El.get('ul#foo'), [
   El.generate('li.bar', {innerText: 1}),
   El.generate('li.baz', {innerText: 2}),
   El.generate('li.qux', {innerText: 3}),
]);

// <ul id="foo">
//   <li class="bar">1</li>
//   <li class="baz">2</li>
//   <li class="qux">3</li>
// </ul>
```
<a name="El.create"></a>

### El.create(selector) ⇒ <code>HTMLElement</code>
**Kind**: static method of <code>[El](#El)</code>  

| Param | Type | Description |
| --- | --- | --- |
| selector | <code>String</code> | (tag [, id, class]) |

**Example**  
```js
El.create('div');
// <div></div>

El.create('section#foo.bar.baz');
// <section id="foo" class="bar baz"></section>

El.create('#foo.bar.baz');
// <div id="foo" class="bar baz"></div>
```
<a name="El.setAttribute"></a>

### El.setAttribute(element, attrs) ⇒ <code>HTMLElement</code>
**Kind**: static method of <code>[El](#El)</code>  

| Param | Type |
| --- | --- |
| element | <code>HTMLElement</code> | 
| attrs | <code>Object</code> | 

**Example**  
```js
El.setAttribute(El.get('div'), {
   id: 'foo',
   class: 'bar baz'
});
// <div id="foo" class="bar baz"></div>
```
<a name="El.style"></a>

### El.style(element, styles) ⇒ <code>HTMLElement</code>
**Kind**: static method of <code>[El](#El)</code>  

| Param | Type |
| --- | --- |
| element | <code>HTMLElement</code> | 
| styles | <code>Object</code> | 

**Example**  
```js
El.style(El.get('div'), {
   width: '100px',
   height: '100px',
   background: 'blue'
});
// <div style="width: 100px; height: 100px; background: blue"></div>
```
<a name="El.innerHTML"></a>

### El.innerHTML(element, html) ⇒ <code>HTMLElement</code>
**Kind**: static method of <code>[El](#El)</code>  

| Param | Type |
| --- | --- |
| element | <code>HTMLElement</code> | 
| html | <code>String</code> | 

**Example**  
```js
El.innerHTML(El.get('section'), '<div>Hello World</div>');

// <section>
//   <div>Hello World<div>
// </section>
```
<a name="El.innerText"></a>

### El.innerText(element, text) ⇒ <code>HTMLElement</code>
**Kind**: static method of <code>[El](#El)</code>  

| Param | Type |
| --- | --- |
| element | <code>HTMLElement</code> | 
| text | <code>String</code> | 

**Example**  
```js
El.innerText(El.get('div'), 'Hello World');
// <div>Hello World<div>
```
<a name="El.generate"></a>

### El.generate(selector, options) ⇒ <code>HTMLElement</code>
**Kind**: static method of <code>[El](#El)</code>  

| Param | Type |
| --- | --- |
| selector | <code>String</code> | 
| options | <code>Object</code> | 

**Example**  
```js
El.generate('ul', {
   attribute: {
     id: 'foo',
     class: 'bar baz'
   },
   style: {
     width: '50%'
   },
   children: [
     El.generate('li', {innerHTML: 1}),
     El.generate('li', {innerHTML: 2}),
     El.generate('li', {innerHTML: 3}),
     El.generate('li', {innerHTML: 4})
   ]
});

// <ul id="foo" class="bar baz" style="width: 50%;">
//   <li>1</li>
//   <li>2</li>
//   <li>3</li>
//   <li>4</li>
// </ul>
```
<a name="El.get"></a>

### El.get(selector) ⇒ <code>HTMLElement</code>
**Kind**: static method of <code>[El](#El)</code>  

| Param | Type |
| --- | --- |
| selector | <code>String</code> | 

**Example**  
```js
El.get('div');
// <div></div>

El.get('span#foo.bar');
// <span id="foo" class="bar"></span>
```
<a name="El.getAll"></a>

### El.getAll(selector) ⇒ <code>NodeList</code>
**Kind**: static method of <code>[El](#El)</code>  

| Param | Type |
| --- | --- |
| selector | <code>String</code> | 

**Example**  
```js
El.getAll('div');
// [div, div, div, ...*]

El.getAll('span.foo');
// [span.foo, span.foo, span.foo, ...*]
```
<a name="El.insertAdjacentHTML"></a>

### El.insertAdjacentHTML(element, position, html) ⇒ <code>HTMLElement</code>
**Kind**: static method of <code>[El](#El)</code>  

| Param | Type | Description |
| --- | --- | --- |
| element | <code>HTMLElement</code> |  |
| position | <code>String</code> | beforeBegin|afterBegin|beforeEnd|afterEnd |
| html | <code>String</code> |  |

**Example**  
```js
// <div id="test">
//   <span>World</span>
// </div>

El.insertAdjacentHTML(El.get('#test'), 'beforeBegin', '<span>Hello</span>');
// <span>Hello</span>
// <div id="test">
//   <span>World</span>
// </div>

El.insertAdjacentHTML(El.get('#test'), 'afterBegin', '<span>Hello</span>');
// <div id="test">
//   <span>Hello</span>
//   <span>World</span>
// </div>

El.insertAdjacentHTML(El.get('#test'), 'beforeEnd', '<span>Hello</span>');
// <div id="test">
//   <span>World</span>
//   <span>Hello</span>
// </div>

El.insertAdjacentHTML(El.get('#test'), 'afterEnd', '<span>Hello</span>');
// <div id="test">
//   <span>World</span>
// </div>
// <span>Hello</span>
```
