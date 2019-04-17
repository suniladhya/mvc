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
Request -> Route Engine in IIS -> MVC RouteHandler executes and retrieves a MVC HttpHandler -> Controller Initiallization -> Action Execution -> Result Execution

The Route Handler provides ASP.Net with HTTP Handler Class, that process the incoming request, after it match to routes.
The HTTP Handler processes the incoming Request, after it match to route.


### Application Start:
Fires, when first request is received.


### Application End:
Fires when a application is completely shuts down Intentionally.
Not a great place to handle application error.

## Viewbag,viewData,TempData
    ViewData["students"] = studentList;
  
<ul>
@foreach (var std in ViewData["students"] as IList<Student>)
{
    <li>
        @std.StudentName
    </li>
}
</ul>

    ViewBag.Id = 1;

    ViewData.Add("Id", 1); // throw runtime exception as it already has "Id" key
    ViewData.Add(new KeyValuePair<string, object>("Name", "Bill"));
    ViewData.Add(new KeyValuePair<string, object>("Age", 20));
	
* ViewData transfers data from the Controller to View, not vice-versa.
* ViewData is derived from ViewDataDictionary which is a dictionary type.
* ViewData's life only lasts during current http request. ViewData values will be cleared if redirection occurs.
* ViewData value must be type cast before use.
* ViewBag internally inserts data into ViewData dictionary. So the key of ViewData and property of ViewBag must NOT match.
