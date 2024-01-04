### Versioning

Versioning allows you to have **different versions** of your controllers or individual routes running within the same application. Applications change very often and it is not unusual that there are breaking changes that you need to make while still needing to support the previous version of the application.

There are 4 types of versioning that are supported:

<table>
  <tr>
    <td><a href='techniques/versioning#uri-versioning-type'><code>URI Versioning</code></a></td>
    <td>The version will be passed within the URI of the request (default)</td>
  </tr>
  <tr>
    <td><a href='techniques/versioning#header-versioning-type'><code>Header Versioning</code></a></td>
    <td>A custom request header will specify the version</td>
  </tr>
  <tr>
    <td><a href='techniques/versioning#media-type-versioning-type'><code>Media Type Versioning</code></a></td>
    <td>The <code>Accept</code> header of the request will specify the version</td>
  </tr>
  <tr>
    <td><a href='techniques/versioning#custom-versioning-type'><code>Custom Versioning</code></a></td>
    <td>Any aspect of the request may be used to specify the version(s). A custom function is provided to extract said version(s).</td>
  </tr>
</table>

#### URI Versioning Type

URI Versioning uses the version passed within the URI of the request, such as https://example.com/v1/route and https://example.com/v2/route.

> **Notice** 
> With URI Versioning the version will be automatically added to the URI after the <a href="faq/global-prefix">global path prefix</a> (if one exists), and before any controller or route paths.

To enable URI Versioning for your application, do the following:

```py title="main.py" linenums="1"
app = NestApplication( AppModule )

app.enableVersioning(type=VersioningType.URI)

app.listen(port=3000)
```

> **Notice** 
> The version in the URI will be automatically prefixed with `v` by default, however the prefix value can be configured by setting the `prefix` key to your desired prefix or `false` if you wish to disable it.

> info **Hint** The `VersioningType` enum is available to use for the `type` property and is imported from the `nest.common` package.


#### Header Versioning Type

[ ... ]

#### Media Type Versioning Type

[ ... ]

#### Custom Versioning Type

[ ... ]

#### Usage

[ ... ]

#### Controller versions

[ ... ]

#### Route versions

[ ... ]

#### Multiple versions

[ ... ]

#### Version "Neutral"

[ ... ]

#### Global default version

If you do not want to provide a version for each controller/or individual routes, or if you want to have a specific version set as the default version for every controller/route that don't have the version specified, you could set the `defaultVersion` as follows:

```py title="main.py" linenums="1"
app = NestApplication( AppModule )

app.enableVersioning(
  type=VersioningType.URI, 
  defaultVersioning='2'
)

app.listen(port=3000)
```

#### Middleware versioning

[ ... ]