# DOTNET/C#

## Recommended nuget packages

- Mapster
- Microsoft.Extensions.Logging
- Quartz
- Swashbuckle.AspNetCore

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

// Avoid
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

1. Use `ActionResult` or `Task<ActionResult>` for async
```cs
public ActionResult GetData()
{
}

public async Task<ActionResult> GetDataAsync()
{
}

```
2. Use `StatusCode` to set exact status
```cs
// Correct
return StatusCode(StatusCodes.Status200OK, items);
return StatusCode(StatusCodes.Status204NoContent);
return StatusCode(StatusCodes.Status500InternalServerError);

// Avoid
return Ok(items);
```

3. Services always with Dto Models
   - Create (Create, Add, Insert)
   - Change (Change, Edit, Update)
   - Delete (Delete, Remove) (`delete` naming can`t use in javascript)
   - Exists (with S on he/she/it)
   - `Nothing` (Get, Read)
   
4. Services with Request, Response suffix {Resource/Action}Request, {Resource/Action}Response
   - CustomerCreateRequestDto
   - CustomerChangeRequestDto
   - CustomerDeleteRequestDto
   - CustomerExistsRequestDto
   - CustomerRequestDto (Get)
6. Repositories we do not use `Dto` Models, here should be created own models with the configuration for the database mapper.
