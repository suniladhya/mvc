# mvc
## Polymophism with Actions
* Polymorphism is a feature of c#, So It should be allowed in MVC.
* In MVC,the Actions are invoked through the URI. So we can not duplicate the url names.
* To achieve polymorphism, Attributes can be used. OR id (Which is optional can be changed to Mandatory)

    ```
    public ActionResult GetById(int id)
    {
        return View();
    }
    
    [ActionName("find")]
    public ActionResult GetById(int id)
    {
        return View();
    }
    
## Lifecycle
[1](https://www.dotnetinterviewquestions.in/article_explain-mvc-application-life-cycle_210.html)
