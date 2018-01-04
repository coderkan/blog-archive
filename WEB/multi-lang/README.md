# Multi Language With JQuery

Hi everyone,

This post I will show you how to add multi language your web site works with **JQuery**. 

What is JQuery?

**JQuery** is a fast, small and  cross-platfom JavaScript library for client-side scripting of HTML. It has HTML document manipulation, event handling, animation. 

It has also developed OpenSource project under MIT License. Find out on [Github](https://github.com/jquery/jquery).

For more detail about **JQuery** you can search and find out more information visit official [website](https://jquery.com/).

Lots of time we need to add multi language our web projects. I will demonstrate how to add simply it.  

Let's go to code!!!

Firstly we have to add **JQuery** libraries, you can easy to find on official [website](https://code.jquery.com/). 
I will use below jquery library.

```html
<script
src="https://code.jquery.com/jquery-2.2.4.min.js"
integrity="sha256-BbhdlvQf/xTY9gja0Dq3HiwQF8LaCRTXxZKRutelT44="
crossorigin="anonymous"></script>
```

We have to add this script in html head. 

After added this library you can write your html code. 
I will use **name** tag and **caption** tag. 

```html
<h1 name="translate" caption="h1">Hi H1 tag</h1>
```

I added name **translate** and give the caption name **h1**. 


After finished our html code then we can focus our jQuery code.
First, we create a file that name is **translate.js** under project files. And add this script to your html **head** like below.

```html
<script src="translate.js"></script>
```

After added this script we continiue to write JQuery codes. Define a function **getLangResources()** like below.

```javascript
function getLangResources(){
    // Define arrays how many language you want to translate
    var tr = new Array();
    var en = new Array();
    // caption tag name
    tr['hello_world'] = "Merhaba Dünya"; 
    en['hello_world'] = "Hello World";
    
    // Added new array defined arrays.
    var resources = new Array();
    resources['tr'] = tr;
    resources['en'] = en;
    
    return resources;
}
```

We have defined an array which is needed language translate. And we put it caption names and translated values. This is very important function.

After that we need to write another function that name is **changeLanguage(lng)** like below.

```javascript
function changeLanguage(lng){
var resources = getLangResources()[lng];
$("h1[name='translate']").each(function(i, elt){
    $(elt).text(resources[$(elt).attr("caption")]);
});
}
```

Above code you have search **h1** tags that name is **translate** and find out **attr** tag is **caption** and change text it given language value. For Turkish **tr** and for English type **en**. 

When document is ready you can simply load languages values with **changeLanguage** function and **click** event. 


```javascript
$(function() { 
    // Default Language
    changeLanguage("en");
 
    // Tr button click
    $("#tr_button").click(function(){
        changeLanguage("tr");
    });

    //Eng button click
    $("#eng_button").click(function(){
        changeLanguage("en");
    });
});
``` 

Adding multi language in your web site has lots of way. I have showed you one of them. I hope this helps you in your projects.

You can find full project on my [Github](https://github.com/coderkan/multi-language-jquery) page. 

I hope you enjoy reading.

Have a nice coding...