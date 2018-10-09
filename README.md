# Coding Guidelines & Structure Guidelines

## General Project

### Project Naming

| Structure  | Example |
| ------------- | ------------- |
| Company.ProjectName  | Microsoft.Owin |
| Brand.ProjectName  | Nager.Date |

### Project Structure

    ├── Nager.Date                    # Solution
    │   ├── Nager.Date                # Library Project
    │   ├── Nager.Date.TestUI         # GUI Project (optional)
    │   ├── Nager.Date.TestConsole    # Console Project (optional)
    │   ├── Nager.Date.UnitTest       # Unit Test Project (optional)

## Recommended nuget packages

- Mapster
- log4net
- Quartz
- Swashbuckle

## C#

1. Use PascalCasing for class names and method names.
2. Use camelCasing for method arguments and local variables.
3. Add every class in a own file, set the the class name same as file name.
4. Do vertically align curly brackets.
5. Sort Usings ascending.
6. Do not use Underscores in identifiers. Exception: Prefix private variables with an underscore.
```cs
// Correct
private string _description;
private string _hostName;

//Avoid
private string description;
private string host_Name;
```
7. Use Implicitly Typed Local Variables `var`
```cs
var description = "test";
```
8. Do prefix interfaces with the letter `I`
```cs
public interface IDataRepository
{
}
```
## asp.net

1. Use `IActionResult` or `Task<IActionResult>`
```cs
public IActionResult GetData()
{
}

public async Task<IActionResult> GetDataAsync()
{
}

```
2. Use `StatusCode` to set exact status
```cs
// Correct
return StatusCode(StatusCodes.Status200OK, items);
return StatusCode(StatusCodes.Status204NoContent);
return StatusCode(StatusCodes.Status500InternalServerError);

//Avoid
return Ok(items);
```

## Vue.js

1. `v-if`
```html
// Correct
<div v-if="hostName">{{hostName}}</data>

//Avoid
<div v-if="hostName !== null">{{hostName}}</data>
```
2. Use Filters to format values
```html
filters: {
  moment: function (date) {
    return moment(date).fromNow();
  }
}

<span>{{ date | moment }}</span>
```
