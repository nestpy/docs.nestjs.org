### Modules

A module is a class annotated with a `@Module()` decorator. The `@Module()` decorator provides metadata that **Nest** makes use of to organize the application structure.

Each application has at least one module, a **root module**. The root module is the starting point Nest uses to build the **application graph** - the internal data structure Nest uses to resolve module and provider relationships and dependencies. While very small applications may theoretically have just the root module, this is not the typical case. We want to emphasize that modules are **strongly** recommended as an effective way to organize your components. Thus, for most applications, the resulting architecture will employ multiple modules, each encapsulating a closely related set of **capabilities**.

The `@Module()` decorator takes a single object whose properties describe the module:

|               |                                                                                                                                                                                                          |
| ------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `providers`   | the providers that will be instantiated by the Nest injector and that may be shared at least across this module                                                                                          |
| `controllers` | the set of controllers defined in this module which have to be instantiated                                                                                                                              |
| `imports`     | the list of imported modules that export the providers which are required in this module                                                                                                                 |
| `exports`     | the subset of `providers` that are provided by this module and should be available in other modules which import this module. You can use either the provider itself or just its token (`provide` value) |

The module **encapsulates** providers by default. This means that it's impossible to inject providers that are neither directly part of the current module nor exported from the imported modules. Thus, you may consider the exported providers from a module as the module's public interface, or API.

#### Feature modules

The `SnakesController` and `SnakesService` belong to the same application domain. As they are closely related, it makes sense to move them into a feature module. A feature module simply organizes code relevant for a specific feature, keeping code organized and establishing clear boundaries. This helps us manage complexity and develop with [SOLID](https://en.wikipedia.org/wiki/SOLID) principles, especially as the size of the application and/or team grow.

To demonstrate this, we'll create the `SnakesModule`.

```py title="snakes_controller.py" linenums="1" hl_lines="1 3"
from nest.common.decorator import Module # (1)
from .snakes_controller import SnakesController
from .snakes_service import SnakesService

@Module( # (2)
    controllers=[SnakesController]
    providers=[SnakesService]
)
class SnakesModule:
    pass

```

1.  :man_raising_hand: I'm a code annotation! I can contain `code`, __formatted
    text__, images, ... basically anything that can be written in Markdown.

2.  :man_raising_hand: I'm a code annotation! I can contain `code`, __formatted
    text__, images, ... basically anything that can be written in Markdown.

Above, we defined the SnakesModule in the Snakes.module.ts file, and moved everything related to this module into the Snakes directory. The last thing we need to do is import this module into the root module (the AppModule, defined in the app.module.ts file).

```py title="snakes/snakes_module.py" linenums="1" hl_lines="1 5"
from nest.common.decorator import Module # (1)
from .snakes.snakes_module import SnakesModule

@Module( # (2)
    imports=[SnakesModule]
)
class AppController:
    pass

```

1.  :man_raising_hand: I'm a code annotation! I can contain `code`, __formatted
    text__, images, ... basically anything that can be written in Markdown.

2.  :man_raising_hand: I'm a code annotation! I can contain `code`, __formatted
    text__, images, ... basically anything that can be written in Markdown.

#### Shared modules

[ ... ]

#### Module re-exporting

[ ... ]

#### Dependency injection

[ ... ]

#### Global modules

[ ... ]

#### Dynamic modules

[ ... ]
