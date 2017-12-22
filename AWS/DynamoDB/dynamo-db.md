# NOSQL

SQL | NoSQL
--- | ---
Optimized for storage | optimized for compute
normalized / relational | Denormalized / hierarchical
Adhoc queries | instantiated views
scale vertically | scale horizontally
good for OLAP | Built for OLTP at scale

# DynamoDb

- fully managed NOSQL service
- Document - key value store

#### Table Structure
- contains items and attributes
- mandatory partition key - equality queries only
- optional sort key
  - model 1:N relationships
  - enables rich query capabilities - range queries
- sequential read

#### Partition Keys
- Partition key uniquely identifies an items
- used for building unordered hash index
- allows table to be partitioned for scale
- hashes are chunked in key spaces

#### Scaling
- scaling is achieved through partitioning tables across multiple storage nodes
- throughput - provisioned at table level
  - controlled by aws user
    - read capacity
    - write capacity
- size
  - every 10GB of inserts go into another partition
  - max item size 400kb
--------
- Reads
  - in dynamodb replication happens across 3 nodes
  - reads are automatically consistent
  - eventually consistent - turned off by default - more cheaper 50%
  - strictly consistent - read after write consistency

-----
#### Partitioning Math
- by size - total size / 10 GB
- by capacity - total RCU / 3000 + total WCU / 1000  
partition = ceiling (MAX (capacity, size))
- RCUs and WCUs are uniformly spread across partitions

throttling
- hot Keys for non uniform work loads - its a problem
- hot data and cold data
- heat  maps

### hierarchical data storage
- use composite sort key to define a hierarchy  

productID | type  
--- | ---  
1 | albumID
1 | albumID : trackID

- store hierarchy as json attributes

-------
### Stored Procedures
- Use Dynamodb streams and AWS Lambda
