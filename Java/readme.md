1. What are the factors on which method overloading depends on? Is return type of a method one of them?

- Method overloading is a feature that allows a class to have multiple methods with the same name, but with different parameters. There are 3 factors affecting method overloading in Java:

- Number of parameters in the method.
- Data type of parameters.
- Order of parameters.

- The return type of a method **doesn't** affect method overloading. So if we have two functions with same parameter count, sequence and datatype but different return type, it will throw an error.
