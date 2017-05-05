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