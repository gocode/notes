C#
=============
Properties
	* public string Name
	  {
    	get
    	{
    		return Name;
    	}	
    	set
    	{
    		Name = value;
    	}
	  }
Indexer
	*	public T this[int i]
	    {
	        get
	        {
	            return arr[i];
	        }
	        set
	        {
	            arr[i] = value;
	        }
	    }
	* index need not be integer
Destructor
	* similar to constructor but prefixed with ~
	* calls Finalize() method
Object initialization
	* var o = new T() { p1 = "", p2 = ""};
Anonymous objects
	* var o = new { name = "mohan", age = 25};
Nullable types
	* T? ~ Nullable<T>
	* HasValue property
	* Value property
	* GetValueOrDefault() method
	* nested nullable not allowed
	* ?? assign a value if null; y = x ?? -1
Delegates
	* analogy to function type
	* create a delegate type with method signature using delegate keyword
	* create an instance of delegate type passing method
	* method can be static
Events
	* Events aren't delegate instances
	* created similar to delegate instance but with 'event' keyword
	* events cannot be called outside the class regardless of access specifier
	* events can be subscribed/unsubscribed from outside the class
	* delegates can subscribe to events with +=
	* delegates can unsubscribe from events with -=
Action and Func
	* both are delegates
	* Func returns a value
	* Action does not return a value
Predicate
	* special case of Func
	* Func<T, bool>
Extension Methods
	* can be created for classes and interfaces
	* defined as static
	* first parameter is the type the method is for 
	* first method is preceded by 'this' modifier
	* the namespace containing the ext. method should be imported
Generics 
	* class, interface and  methods
	* open constructed - type specified
	* closed constructed - type not specified
	* 'where' keyword used to specify constraints
	* constraints can be superclass or of same type
	* new() constraint used to imply that the type is created by the class
ref and out parameters
	* in ref object is initialized before sent to method
	* in out object is initialized inside the method
Partial methods
	* must be private void
	* must be within partial class
	* can have one or no implementation
	* if no implementation declaration is removed by compiler
	* cannot have out parameter
	* can have ref parameter
async and await
	* improves app response
	* async modifier is used for the method
	* method can return Task<T> or Task or void 
	* await on Task<T> will suspend the method untill the async method is complete
	* Task is used when the method does not return an operand
	* async methods that return void cannot be awaited and its exceptions cannot be caught
	* ref and out parameters cannot be used in async methods
Dynamic type
	* static type but bypasses type checking
	* overload resolution also takes place at run time
	* dynamic binding
Attributes
	* supply info to compiler/runtime
	* inherit 'System.Attribute' and marked with AttributeUsage attribute
	* convention - end with the word "Attribute" 
yield
	* temporarily return from a method
	* yield is specified in front of return keyword
covariance and contravariance
	* .net supports covariance and contravariance
	* covariance - methods return more derived types
	* contravariance - methods accept parameters that have less derived types
	* used to assign functions to delegates where the signatures do not exactly match
Polymorphism
	* 'virtual' keyword used to indicate that the base class implementation should be used
	* 'override' keyword is used to override a virtual member
 	* 'new' keyword is used to override a non virtual member
 	* 'sealed' keyword is used to stop a member from being virtual
 	* 'base' keyword is used to access base class virtual members from derived class
 	* the base class member is called when non virtual member of derived class is called after being cast to base class
Iterator
	* IEnumerable
	* GetEnumerator on IEnumerable gives IEnumerator

MVC
=============
Routes
	* RouteCollection.MapRoute("Default","{controller}/{action}/{id}",new {controller="Home",action="Index",id=""});
Controller
	* inherits Controllers class
Action
	* method inside Controller
ActionResult
	* ActionResult
ActionSelector
	* [HttpPost]
	* [HttpGet]
ActionFilter
	* [HandleError]
	* [OutputCache(Duration=10)]
	* [Authorize]
	* custom filter can be created by extending 'ActionFilterAttribute'
	* OnActionExecuting, OnActionExecuted, OnResultExecuting, OnResultExecuted
Razor Expression, code block
	* @
	* @{ }
Layout views
	* _Layout.cshtml under Views/Shared has the master page with doctype, head section etc
Partial views
	* as a convention starts with _
	* @Html.Partial("view", model)
HTML helpers
	* @Html.ActionLink(link text, action, new { id = 10})
	* @Html.BeginForm
	* @Html.LabelFor(m => m.Name)
	* @Html.EditorFor(m => m.Name)
	* @Html.ValidationMessageFor(m => m.Name)
Ajax helpers
	* @Ajax.BeginForm
Url helper
	* @Url.ActionUrl
	* @Url.Content
	* @Url.Encode
Script helpers
Custom helper
web.config
	machine.config
	web.config - system wide
	web.config 
	web.config in Views folder
Cache
Validation annotations
	* [Required(ErrorMessage="Required")]
	* [Range(5,100,ErrorMessage ="Movies cost between $5 and $100.")]
Custom validations
Security - Anonymous, Authorize and ValidateAntiForgeryToken
Mass assignment - Bind annotation

WebAPI
=========
ApiController
WebApi routes
HttpRequestMessage
HttpResponseMessage
HttpClient

Entity Framework	
=================
Package Manager Console
Database migrations
DBContext
DBSet

LINQ
========
IEnumerable
IQueryable
Join
Group
let and into

SQL Server
===========

MSTest
========
TestClass
TestMethod
ControllerContext


