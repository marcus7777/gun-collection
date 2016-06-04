Use Gun without knowing the Gun API.

Web-component for GUNDB (http://gun.js.org/enterprise/)

and Polymer (https://www.polymer-project.org/1.0/)

## Discription

`<gun-collection>` provides full CRUD operations on a gun collection 

## Member of a collection of Gun components.
`<gun-client>`      http://stefdv.github.io/gun-client/components/gun-client/

`<gun-collection>`

`<gun-datatable>`   Working on API docs

`<gun-tagger>`      Working on API docs

`<gun-models>`      Working on API docs

`<gun-tags>`        Working on API docs

`<gun-sets>`        Working on API docs

`<gun-todo>`        Working on API docs



## Dependencies 
`<gun-client>` : https://github.com/Stefdv/gun-client

## Usage

Just provide it with a name of your collection and it returns your records.

But wait!! It not only returns them...it updates them as well !

Oh..end you can do  

```
var gc = document.querySelector('gun-collection');
gc.createRecord({key:'User1',data:{name:'User1',age:30,...}});
gc.getRecord('User1');
gc.updateRecord({key:'User1',data:{age:31}});
gc.removeRecord('User1');
```
## Example:
`<gun-collection id="users" name="Users" records="{{Users}}"></gun-collection>`

In your `<x-app>` ;

```
this.$.users.createRecord({key:'Stef',data:{name:'Stef',Country:'The Netherlands'}});
this.$.users.updateRecord({key:'Stef',data:{Country:'USA'}});
this.$.users.removeRecord('Stef');
```
And in your DOM:

```
<gun-collection id="users" name="Users" records="{{Users}}"></gun-collection>
<ul>
<template is="dom-repeat" items="{{Users}}" as="user">
  <li>[[user.name]] from [[user.Country]]</li>
</template>
</ul>
```
## And then some

`<gun-collection>` uses a callback `.map()`  to listen for changes on the records.

It also does al kind of filtering on them (leaving out 'nulled' items and items that are 'unTagged').
But what if you need to provide your own callback? No problem...`<gun-collection>` has a function that can be overriden. `mapCallback()` . This function is called from the gun-collections callback so you can manipulate the records before they come back to you.

@element gun-collection
@blurb Provides an easy starting point for a Gun based application.
