# **Laravel Foundation**
If you reading this README.md that means you already know what is laravel. I hope you know php, mysql, html, css, and javascript. 

## what is laravel?
Laravel is a web framework. It provides bunch of efficient codes which are reusable in every web application so that we don't need to write same code again and again. Moreover the framework provided codes are clean and developed by maintaining proper design pattern and architecture. If you read only laravel's source code you will be astonished with the magic of object oriented programming. It is open source and popular among web developers. It provides lots of features which are very essential for a web application. 


## As you read from above, laravel itself has a proper architecture. Now question is what is that architecture? 

The answer is MVC. The complete form is model view controller. what actually it is? Let's dig out step by step.

Suppose I want to order a smart phone from a shopping app. when my request will receive the shopping app, what will happen? Actually the app is located (deployed) somewhere in the world (in any server). 

So. 
1.Somebody will receive my request for smart phone. It is actually Routes who define the url end point.These end points are uniqu and each end points are associated with With a specific function. Basically These functions are called controller. 

2.When the dedicated function/controller will read my request, It will try to give some response to me but how? To prepare response It need some data related to Smart Phone. The application has a model Called SmartPhone. Through this model, it will communicated with database and fetch some data related to SmartPhone. When the data will reach to the controller, it will send the response.

3. But how it will send the response? First It will send the fetched data to a template or a frame. This frame is called view. This view will be send back to me. 

This whole pattern is known as MVC architecture. It is a popular architecture and most of the medium scale web app is written by following this pattern. 



# What do you need to learn Laravel?
1. Code Editor :)
2. Terminal
3. php 
4. mysql
5. composer

by googling you should be able to install all the tools. 


# how to install Laravel? Type follwong into your terminal:
`composer create-project laravel/laravel example-app`

composer is a package manager of php application. Most of the programming language has a dependency manager. Composer is build for managing php application. 

Explaination:
1. create-project means simply create new project. 
2. laravel/laravel is indicating github repo.
3. example-app is the name of your desired application which you are going to create.


# How to look a laravel boiler plate? what is included in a fresh laravel installation? How to run laravel web application?
1. app
2. bootstrap
3. config
4. database
5. lang 
6. public
7. resource
8. Routes
9. storage
10. tests
11. vendors
12. .editorconfig
13. .env
14. .env.example
15. .gitattributes
16. .gitignore
17. artisan
18. composer.json
19. composer.lock
20. package.json
21. phpunit.xml
22. README.md
23. vite.config.js 

Don't get overwhelmed by looking so many directories. You won't understand everything at once. Just go slowly with patience. First of all you need to run laravel web application :). 

write the following in your terminal:
`php artisan serve`

A development server will bootup and url will be:
`http://127.0.0.1:8000`

go to that url and a page will be opened which is the  default home page.

Now the question is how, when, where the home page is loaded?

I told you every request is received by routes. If you go to routes directory, you will get: 
1. api.php
2. channels.php
3. console.php
4. web.php

Now focus on only web.php. 
you will see :

`Route::get('/', function () {
    return view('welcome');
});`

here the code is Intuitive. '/' means the home url. when the '/' will be hit, the corresponding function will be run. It is returning a view which is actually a html like file. You can guess the file name is welcome. Now the question is where is this file?

You will get that file inside of resources directory.
1. css
2. js
3. views
go to views. You will see welcome.blade.php. Notice when we told the file name to view function we didn't mention .blade.php. Laravel will understand automatically. 


# sending different types of response. 

1.returning a string
<pre>
Route::get('/some-end-point', function(){       
    return "dummy response";   
});
</pre>

2.returning a json
<pre>
Route::get('/some-end-point', function(){
    return ["foo" => "bar"];
});
</pre>

3.returning a html tag
<pre>
Route::get('/some-end-point', function(){
    return &#x22;&#x3C;h1&#x3E;Awesome Html tag&#x3C;/h1&#x3E;&#x22;;
});
</pre>

4. returning a view file.
<pre>
Route::get('/some-end-point', function(){
    return view("somefile");
});
</pre>

# how to add a css and js file with blade file?
1. put your cs/js file inside of public folder (must important***)
2. link with blade using link tag and right path specified.
Example:
`<link href="/x.css"`
`<script src="/y.js"></script>"`







