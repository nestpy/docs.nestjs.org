### Controllers

Controllers are responsible for handling incoming **requests** and returning **responses** to the client.

A controller's purpose is to receive specific requests for the application. The **routing** mechanism controls which controller receives which requests. Frequently, each controller has more than one route, and different routes can perform different actions.

In order to create a basic controller, we use classes and **decorators**. Decorators associate classes with required metadata and enable Nest to create a routing map (tie requests to the corresponding controllers).

#### Routing

```py title="snakes_controller.py" linenums="1" hl_lines="1 4"
@Controller('snakes') # (1)
class AppController:
    
    @Get() # (2)
    async def findAll() -> str:
        return "This action returns all snakes"
```

1.  :man_raising_hand: I'm a code annotation! I can contain `code`, __formatted
    text__, images, ... basically anything that can be written in Markdown.

2.  :man_raising_hand: I'm a code annotation! I can contain `code`, __formatted
    text__, images, ... basically anything that can be written in Markdown.

The `@Get()` HTTP request method decorator before the `findAll()` method tells Nest to create a handler for a specific endpoint for HTTP requests. The endpoint corresponds to the HTTP request method (GET in this case) and the route path. What is the route path? The route path for a handler is determined by concatenating the (optional) prefix declared for the controller, and any path specified in the method's decorator. Since we've declared a prefix for every route ( `cats`), and haven't added any path information in the decorator, Nest will map `GET /snakes` requests to this handler. As mentioned, the path includes both the optional controller path prefix **and** any path string declared in the request method decorator. For example, a path prefix of `snakes` combined with the decorator `@Get('breed')` would produce a route mapping for requests like `GET /snakes/breed`.

In our example above, when a GET request is made to this endpoint, Nest routes the request to our user-defined `findAll()` method. Note that the method name we choose here is completely arbitrary. We obviously must declare a method to bind the route to, but Nest doesn't attach any significance to the method name chosen.

This method will return a 200 status code and the associated response, which in this case is just a string. Why does that happen? To explain, we'll first introduce the concept that Nest employs two **different** options for manipulating responses:

<table>
  <tr>
    <td>Standard (recommended)</td>
    <td>
      Using this built-in method, when a request handler returns a dictionary or array, it will <strong>automatically</strong>
      be serialized to JSON. When it returns a Python primitive type (e.g., <code>str</code>, <code>int</code>, <code>bool</code>), however, Nest will send just the value without attempting to serialize it. This makes response handling simple: just return the value, and Nest takes care of the rest.
      <br />
      <br /> Furthermore, the response's <strong>status code</strong> is always 200 by default, except for POST
      requests which use 201. We can easily change this behavior by adding the <code>@HttpCode(...)</code>
      decorator at a handler-level (see <a href='controllers#status-code'>Status codes</a>).
    </td>
  </tr>
  <tr>
    <td>Library-specific</td>
    <td>
      We can use the library-specific (e.g., FastAPI) <a href="https://expressjs.com/en/api.html#res" rel="nofollow" target="_blank">response object</a>, [ ... ]
    </td>
  </tr>
</table>

#### Request object

[ ... ]

#### Resources

Earlier, we defined an endpoint to fetch the cats resource (**GET** route). We'll typically also want to provide an endpoint that creates new records. For this, let's create the **POST** handler:

```py title="snakes_controller.py" linenums="1" hl_lines="1 8"
@Controller('snakes')
class AppController:
    
    @Get() # (1)
    async def findAll() -> str:
        return "This action returns all snakes"

    @Post() # (2)
    async def create() -> str:
        return "This action adds a new snake"
```

1.  :man_raising_hand: I'm a code annotation! I can contain `code`, __formatted
    text__, images, ... basically anything that can be written in Markdown.

2.  :man_raising_hand: I'm a code annotation! I can contain `code`, __formatted
    text__, images, ... basically anything that can be written in Markdown.

It's that simple. Nest provides decorators for all of the standard HTTP methods: `@Get()`, `@Post()`, `@Put()`, `@Delete()`, `@Patch()`, `@Options()`, and `@Head()`. In addition, `@All()` defines an endpoint that handles all of them.

#### Route wildcards

[ ... ]

#### Status code

[ ... ]

#### Headers

[ ... ]

#### Redirection

[ ... ]

#### Route parameters

[ ... ]

#### Sub-Domain Routing

[ ... ]

#### Scopes

[ ... ]

#### Asynchronicity

[ ... ]

#### Request payloads

[ ... ]

#### Handling errors

[ ... ]

#### Full resource sample

[ ... ]

#### Getting up and running

[ ... ]

#### Library-specific approach

[ ... ]
