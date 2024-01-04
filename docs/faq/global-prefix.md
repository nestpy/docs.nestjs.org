### Global prefix

To set a prefix for **every route** registered in an HTTP application, use the `setGlobalPrefix()` method of the `INestApplication` instance.

```py title="main.py" linenums="1"
app.setGlobalPrefix('/api')
```

You can exclude routes from the global prefix using the following construction:

[ ... ]

Alternatively, you can specify route as a string (it will apply to every request method):

[ ... ]