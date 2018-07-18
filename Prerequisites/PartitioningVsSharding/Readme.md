- [index]()

# Partitioning vs Sharding

**Partitioning** is a general term used to describe the act of breaking up your logical data elements into multiple entities for the purpose of performance, availability, or maintainability.  

**Sharding** is the equivalent of **horizontal partitioning**. When you shard a database, you create replica's of the schema, and then divide what data is stored in each shard based on a shard key. For example, I might shard my customer database using CustomerId as a shard key - I'd store ranges 0-10000 in one shard and 10001-20000 in a different shard.  When choosing a shard key, the DBA will typically look at data-access patterns and space issues to ensure that they are distributing load and space across shards evenly.  

**Vertical partitioning** is the act of splitting up the data stored in one entity into multiple entities - again for space and performance reasons.  For example, a customer might only have one billing address, yet I might choose to put the billing address information into a separate table with a CustomerId reference so that I have the flexibility to move that information into a separate database, or different security context, etc.    

To summarize - partitioning is a generic term that just means dividing your logical entities into different physical entities for performance, availability, or some other purpose.  **Horizontal partitioning, or sharding**, is replicating the schema, and then dividing the data based on a shard key.  **Vertical partitioning** involves dividing up the schema (and the data goes along for the ride).  

Final note: you can combine both horizontal and vertical partitioning techniques - sometimes required in big data, high traffic environments.
