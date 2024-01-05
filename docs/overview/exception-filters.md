### Exception filters

Nest comes with a built-in **exceptions layer** which is responsible for processing all unhandled exceptions across an application. When an exception is not handled by your application code, it is caught by this layer, which then automatically sends an appropriate user-friendly response.

[ ... ]

Out of the box, this action is performed by a built-in **global exception filter**, which handles exceptions of type `HttpException` (and subclasses of it). When an exception is **unrecognized** (is neither `HttpException` nor a class that inherits from `HttpException`), the built-in exception filter generates the following default JSON response:

#### Throwing standard exceptions

[ ... ]

#### Custom exceptions

[ ... ]

#### Built-in HTTP exceptions

[ ... ]

#### Exception filters

[ ... ]

#### Arguments host

[ ... ]

#### Binding filters

[ ... ]

#### Catch everything

[ ... ]

#### Inheritance

[ ... ]
