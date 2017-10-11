# VueJS
----------------------------------------
## I. Introduction
- Vue (pronounced /vjuː/, like view) is a progressive framework.
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

-----------------------------------------------
## II. Constructor
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
        domain : "freetuts.net"
    }
});

```
