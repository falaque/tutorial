Routing:
--------

### Attribute Routing:
``` C#

//for url /home
[Route("home")]
public ActionResult Index()
{
  return View();
}

//for url /, /home and /home/index
[Route("")]
[Route("home")]
[Route("home/index")]
public ActionResult Index()
{
  return View();
}

```
#### Route Parameter
``` C#
//passing id as route params, for url like /home/index/23, where 23 is id.
[Route("homme/index/{id}")]
public ActionResult Index(int id){
  return View();
}

//multiple params, for url like /index/2017/April/23
[Route("index/{year}/{month}/{day}")]
public ActionResult Index(string year, string month, int day)
{
  return View();
}

```

#### Controller Routes

``` C#

[Route("home/{action}")]
public class HomeController:Controller
{
  //following route will override the controller route
  //url: /, /home will work but; /home/index will not work.
  [Route("/")]
  [Route("/home")]
  public ActionResult Index()
  {
    return View();
  }
  
  //url: home/About
  public ActionResult About()
  {
    return View();
  }
  
  public ActionResult Contact()
  {
    return View();
  }
  
}

```

#### Route Constraints
``` C#
/* 
explaination of route: parameter name should be string whose maxlength is 20, if this param is not provided, "some_name" is taken as default value
example url: /person/abc , /person/david , /person
*/ 
[Route("person/{name:maxlength(20)=some_name}")]
public ActionResult Person(string name)
{
    return Content("The person is:" + name);
}

```
