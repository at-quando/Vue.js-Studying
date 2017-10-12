# VueJS
----------------------------------------
### 1.Installation
- Have 2 way: 
  - Add `<script language="javascript" src="https://unpkg.com/vue"></script>` into your file html.
  - Dowload **Development Version**.

### 2. Introduction
#### 2.1 What is VueJS ?
- Vue (/vjuː/) is a progressive framework.
- The core library is focused on the view layer only and is easy to pick up and integrate with other libraries or existing projects.
- Vue have 4 version :
	- VueJS 0.11
	- VueJS 0.12
	- VueJS 1.0
	- VueJS 2.x
- Each version have 2 part
  - Development Version with full warnings and debug mode.
  - Production Version.
- Example:
```javascript
  <!DOCTYPE html>
  <html lang="en">

  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
  </head>

  <body>
  <div id="app-vue">
    {{greet}} !
  </div>
    <script language="javascript" src="https://unpkg.com/vue"></script>
    <script>
      window.onload = function () {
        let app = new Vue({
          el: '#app-vue',
          data: {
            greet: 'hello word'
          }
        })
      }
    </script>
  </body>

  </html>
```
#### 2.2 Declarative Rendering

```html
<div id="app">
  {{greet}}
</div>
```

```javascript
var app = new Vue({
  el: '#app',
  data: {
    greet: 'Hello world!'
  }
})
```
> Hello world !

We have already created our very first Vue app! This looks pretty similar to rendering a string template, but Vue has done a lot of work under the hood. The data and the DOM are now linked, and everything is now reactive.

#### 2.3 Conditionals and Loops
- It’s easy to toggle the presence of an element, too:

```html
<div id="app-3">
  <span v-if="fe">I am FE developer</span>
</div>
```
```javascript
var app2 = new Vue({
  el: '#app-2',
  data: {
    fe: true
  }
})
```
> I am FE developer

Go ahead and enter app2.fe = false in the console. You should see the message disappear.
This example demonstrates that we can bind data to not only text and attributes, but also the structure of the DOM.

There are quite a few other directives, each with its own special functionality. For example, the v-for directive can be used for displaying a list of items using the data from an Array:

```html
<div id="app-4">
  <ol>
    <li v-for="skill in skills">
      {{ skill }}
    </li>
  </ol>
</div>
```
```javascript
var app3 = new Vue({
  el: '#app-3',
  data: {
    skills: ['JavaScript','Css','Html']
  }
})
```
> 1.Javascript
> 2.Css
> 3.Html

In the console, enter app3.skills.push({ skill: 'VueJS ' }). You should see a new item appended to the list.

#### 2.4 Handling User Input
To let users interact with your app, we can use the v-on directive to attach event listeners that invoke methods on our Vue instances:

```html
<div id="app-4">
  <p>{{ message }}</p>
  <button v-on:click="greet">Click me</button>
</div>
```

```javascript
var app4 = new Vue({
  el: '#app-4',
  methods: {
    greet: function () {
      alert('Hello world!');
    }
  }
})

```

Note that in this method we update the state of our app without touching the DOM - all DOM manipulations are handled by Vue, and the code you write is focused on the underlying logic.
Vue also provides the v-model directive that makes two-way binding between form input and app state a breeze:

```html
<div id="app-5">
  <p>Hello {{ name }}!</p>
  <input v-model="name">
</div>
```
```javascript
var app5 = new Vue({
  el: '#app-5',
  data: {
    name: 'somebody'
  }
})
```

#### 2.5 Composing with Components
The component system is another important concept in Vue, because it’s an abstraction that allows us to build large-scale applications composed of small, self-contained, and often reusable components. If we think about it, almost any type of application interface can be abstracted into a tree of components:

![Alt text](.picture/components.png)








-----------------------------------------------
### 2. The Vue Instance
#### 2.1 Creating a Vue Instance
very Vue.js app is bootstrapped by creating a root **Vue** instance with the Vue constructor function:

```javascript
var vm = new Vue({
  // options
})
console.log(vm) // To see more vue instance
```
A **Vue** instance is essentially a ViewModel(vm) as defined in the MVVM pattern. When you instantiate a Vue instance, you need to pass in an options object which can contain options for *data*, *template*, *element* to mount on, *methods*, *lifecycle callbacks* and more. 

-----------------------------------------------
## Properties and Methods
All the properties and methods you want to include Vue must be through the key **data** at initialization. This key **data** is called Proxies for Vue instance when the newly initiated.
```javascript
var vm = new Vue({
    data : {
      greet : 'hello',
      greetUse: function(name){
        console.log('hello ' + name);
      }
    }
});
 console.log(vm.$domain) #=> hello
 vn.
```
