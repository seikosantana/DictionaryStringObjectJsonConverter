# DictionaryStringObjectJsonConverter
System.Text.Json converter to (de)serialize Dictionary&lt;string, object?> with System.Text.Json, based on https://github.com/joseftw/JOS.SystemTextJson.DictionaryStringObject.JsonConverter

## Usage Example

```cs
builder.Services.AddControllersWithViews()
    .AddJsonOptions(options => {
        // Configure for web defaults
        options.JsonSerializerOptions.PropertyNameCaseInsensitive = true;
        options.JsonSerializerOptions.PropertyNamingPolicy = JsonNamingPolicy.CamelCase;
        options.JsonSerializerOptions.NumberHandling = JsonNumberHandling.AllowReadingFromString;

        // Add dictionary deserializer, but deserialize with web defaults
        options.JsonSerializerOptions.Converters.Add(
            new DictionaryStringObjectJsonConverter(new JsonSerializerOptions(JsonSerializerDefaults.Web)));
    })
```
