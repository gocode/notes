JAX-RS
========

Annotations
-----------

	* @Path("path/{variable1}/{variable2: [^/]+?}/")
	* @GET
	* @POST
	* @PUT
	* @DELETE
	* @Produces("text/plain"), @Produces({"application/xml", "application/json"})
	* @Consumes("text/plain"), @Consumes({"text/plain,text/html"})
	
Extracting Request Parameters
-----------------------------

	* @QueryParam("variable")
	* @PathParam("variable")
	* @CookieParam("variable")
	* @FormParam("variable")

@Path("smooth")  
@GET  
public Response smooth(  
        @DefaultValue("2") @QueryParam("step") int step,  
        @FormParam("name") String name,  
        ) { ... }  

To obtain a general map of parameter names and values for query and path parameters, use the following code:  

@GET  
public String get(@Context UriInfo ui) {  
    MultivaluedMap<String, String> queryParams = ui.getQueryParameters();  
    MultivaluedMap<String, String> pathParams = ui.getPathParameters();  
}  
The following method extracts header and cookie parameter names and values into a map:  

@GET  
public String get(@Context HttpHeaders hh) {  
    MultivaluedMap<String, String> headerParams = hh.getRequestHeaders();  
    Map<String, Cookie> pathParams = hh.getCookies();  
}  
In general, @Context can be used to obtain contextual Java types related to the request or response.  

For form parameters, it is possible to do the following:  

@POST  
@Consumes("application/x-www-form-urlencoded")  
public void post(MultivaluedMap<String, String> formParams) {  
    // Store the message  
}  

Subresource Methods
-------------------
Method that has a @Path annotation and handles HTTP requests

Subresource Locators
--------------------
Method that has @Path annotation and returns an object that handles HTTP request

JAX-RS with JAXB
----------------
The below tags can be used to indicate that the service accepts and consules xml.
	* @Consumes("application/xml")
	* @Produces("application/xml")
JAX-RS runtime automatically performs marahall/unmarshall of request/response.

JAX-RS with JSON
----------------
The below tags can be used to indicate that the service accepts and consules JSON.
	* @Consumes("application/json")
	* @Produces("application/json")

In order to consume/produce xml and json the below annotations can be used.
	* @Produces({"application/xml","application/json"})
	* @Consumes({"application/xml","application/json"})

Here the default is xml but json will be returned if the below header is part of request.  
Accept: application/json

JSON will be accepted if the below is part of request.  
Content-Type: application/json