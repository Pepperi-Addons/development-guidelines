# Pepperi Addons Development Guidelines and Best Practices

## Introduction

The following is a list of the development guidelines and best practices for Pepperi Addons.

These guidelines and best practices are used to ensure that the code is written in a way that is consistent with the Pepperi Addons coding standards.

These guidelines should be enforced by code reviewers and developers.


### Addon Name
The name of the addon should be in kebab-case.

The name of the repository should be in kebab-case as well, and should be the same as the addon name.

If the name of the addon changes, the name of the repository should also change.

### Rest API

#### URL
The URL in the REST API should be snake_case.
This should be done for both public and private APIs.

#### Method
In Pepperi REST APIs we use the GET and POST API methods.

GET methods should be used for retrieving data.

POST methods should be used for the following:
* Creating a new resource
* Updating an existing resource
* Deleting an existing resource
* Performing an operation
* Retrieving data when the parameters are either to large to fit in the URL or when their data type is complex.

#### Query Parameters
The query parameters in the REST API should be snake_case.

#### Body Parameters
The body parameters in the REST API should be PascalCase.

#### Response
The response in the REST API should be PascalCase.

### File Names
The file names should be in kebab-case.

Related files should be grouped into folders.

Folder names should be in kebab-case.

### Classes
Class names should be PascalCase.

e.g.
``` typescript
class MyClass {
}
```

Class names should describe the purpose of the class. 

Every class should have a clear purpose.

Every class should have a separate file. the file should be named after the class. eg. `my-class.ts`

Classes should not be very long, when a class is long, it should be split into multiple classes.

Classes that follow a certain design pattern, should have a name that describes the pattern, as well as the purpose of the class. eg. `MyObjectService`, `MyObjectProducer`, `FooCommand`.

### Enums
Enum names should be PascalCase.
The enum values should be PascalCase as well.

e.g.
``` typescript
enum MyEnum {
  MyValue,
  MyOtherValue,
}
```

When defining an enum as a string property that has a fixed set of values, the enum should be defined as follows:

``` typescript
const MyTypes = [
  'Value1',
  'Value2',
];
type MyType = typeof MyTypes[number];
```

This way validation can be done on the enum values in runtime as well.
eg.
``` typescript
function validateMyType(value: MyType) {
  if (!MyTypes.includes(value)) {
    throw new Error(`Invalid value for MyType: ${value}`);
  }
}
```

### Functions
Function names should be camelCase.

e.g.
``` typescript
function myFunction() {
  // ...
}
```

Function parameters should be in camelCase.

eg.
``` typescript
function myFunction(myParameter: string) {
  // ...
}
```

Function names should describe the purpose of the function.

Every function should have one clear purpose.

Functions should not be very long, when a function is long, it should be split into multiple functions. A function that is more than 5 or 6 lines long is considered to be long.

Every function parameter should be typed.

Function return types should be typed.

Do not use `any` as a paramter type unless you are sure that it is necessary.

### Interfaces
Interface names should be PascalCase.

e.g.
``` typescript
interface MyInterface {
  // ...
}
```

Interfaces should be used to describe the shape of the data.
Interfaces do not have to start with an I prefix. Since in typescript interface type describe object properties, and not Interfaces themselves.
In the case when you are using an Interface for defining an interface of an service input to a class, in contrast to a data object input, the interface name should start with I.

e.g.
``` typescript
interface IMyDataSource {
  // ...
}
```

## Angular Projects

### Component Names
Component names should be PascalCase.

The should have a suffix of `Component`.
