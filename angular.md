Angular 2
==========

#### Getting started:
---------------------
[quick start](https://angular.io/guide/quickstart)
* install the angular cli globally.
``` 
npm install -g @angular/cli
```
* create a new project:
```
ng new my-app
```
* serve the application:
```  
cd my-app
ng serve --open
```
#### ng new offline:
-------------------
[stackoverflow answer](https://stackoverflow.com/questions/44127122/create-new-project-offline)

Following steps can be used to create the ng project offline.
* First create only the project structure skipping additional installtions
``` 
ng new ProjectName  --skip-install 
```
* Copy the ***node_modules*** folder from an existing project and paste inside your newly created project 
* try ```ng serve``` #it shouls work, it worked for me.