### Providers

Providers are a fundamental concept in Nest. Many of the basic Nest classes may be treated as a provider – services, repositories, factories, helpers, and so on. The main idea of a provider is that it can be **injected** as a dependency; this means objects can create various relationships with each other, and the function of "wiring up" these objects can largely be delegated to the Nest runtime system.

#### Services

[ ... ]

#### Dependency injection

[ ... ]

#### Scopes

[ ... ]

#### Custom providers

[ ... ]

#### Optional providers

[ ... ]

#### Property-based injection

[ ... ]

#### Provider registration

[ ... ]

Now that we have defined a provider (`SnakesService`), and we have a consumer of that service (`SnakesController`), we need to register the service with Nest so that it can perform the injection. We do this by editing our module file (`snakes_module.py``) and adding the service to the `providers` array of the `@Module()` decorator.

Nest will now be able to resolve the dependencies of the `SnakesController` class.

```py title="snakes_module.py" linenums="1" hl_lines="7 8"
from nest.common.decorators import Module

from snakes.snakes_controller import SnakesController 
from snakes.snakes_service import SnakesService

@Module(
    controllers=[SnakesController], # (1)
    providers=[SnakesService] # (2)
)
class SnakesModule: 
    pass
```

1.  :man_raising_hand: I'm a code annotation! I can contain `code`, __formatted
    text__, images, ... basically anything that can be written in Markdown.

2.  :man_raising_hand: I'm a code annotation! I can contain `code`, __formatted
    text__, images, ... basically anything that can be written in Markdown.


This is how our directory structure should look now:

[ ... ]

#### Manual instantiation

[ ... ]