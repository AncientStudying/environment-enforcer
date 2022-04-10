# Design Approach
Library will start as a subclass of ArgumentParser. Plan is to start by overriding the constructor, add_argument(), add_A and parse_args().

**argument_groups** will not be supported for env or menu args at this time

## __init__(...)
* Will accept same parameters as ArgumentParser
* **environment_vars**: A new parameter that will allow the user to indicate if system environment variables may be used to specify the values default is False
* **use_menu**: A new parameter that will indicate if the application can invoke consolemenu to obtain missing values

## add_args(...)
* Will accept same parameters as ArgumentParser
* **use_getpass**: new parameter indicating if getpass should be used for the input if value is not found. default will be False

## parse_args(...)
* Will accept same parameters as ArgumentParser
* If no parameters are provided values will be obtained from sys.argv and os.environ and a default menu provided
* **envrion_vars**: new parameter with list of environment variables
* **menu_vars**: some form of injected var to simulate the menu inputs - assume simple key-value pairs

Values will be obtained from EnvironmentEnforcer the same way as ArgumentParser
