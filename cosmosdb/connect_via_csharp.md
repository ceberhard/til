## Connect & Query a Cosmos Instance

__*Coded in C# 10.0 (.NET 6.0 Preview)*__

__*Microsoft.Azure.Cosmos version 3.20.1*__

How to connect to and query a Cosmos database and container.

```C#
using Microsoft.Azure.Cosmos;
using System.Collections;

string endpointUri = "<Cosmos Endpoint URI>";
string primaryKey = "<Cosmos Auth Key";
string databaseName = "<Database Name>";
string containerName = "<Container Name>";

CosmosClient cosmosClient = new CosmosClient(EndpointUri, PrimaryKey);
Container programsContainer = cosmosClient.GetContainer(databaseName, containerName);

IEnumerable<DataModel> models = programsContainer.GetItemLinqQueryable<DataModel>(true).Where(m => m.id == 1234);

Console.WriteLine($"Found Models: {models.Count()}");

public class DataModel {
    public string id { get; set; }
    public string Name { get; set; }
}
```

### References:

https://docs.microsoft.com/en-us/dotnet/api/microsoft.azure.cosmos.cosmosclient.getcontainer?view=azure-dotnet

https://docs.microsoft.com/en-us/dotnet/api/microsoft.azure.cosmos.container.getitemlinqqueryable?view=azure-dotnet
