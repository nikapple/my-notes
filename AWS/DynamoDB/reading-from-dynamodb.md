# Reading from DynamoDb

- **querying a bunch of items**

```
AmazonDynamoDB client;
DynamoDB dynamoDB = new DynamoDB(client);
Table table = dynamoDB.getTable("logs");
QuerySpec spec = new QuerySpec()
ItemCollection<QueryOutcome> items = table.query(spec);
Iterator<Item> iterator = items.iterator();
Item item = null;
while (iterator.hasNext()) {
	item = iterator.next();
	System.out.println(item.toJSONPretty());
}
```
