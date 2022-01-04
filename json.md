## Best Ways to Work with JSON

Read json config file from same folder as binary into JsonNode:
<pre>
var configs = JsonNode.Parse(File.ReadAllText($"{AppContext.BaseDirectory}/{ConfigFilename}"));
</pre>

Save a dictionary or some other object to that same config json file above:
<pre>
File.WriteAllText($"{AppContext.BaseDirectory}/{ConfigFilename}", JsonSerializer.Serialize(someObject));
</pre>
