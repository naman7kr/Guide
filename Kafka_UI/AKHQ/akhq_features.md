# AKHQ
> Kafka GUI for Apache Kafka ® to manage topics, topics data, consumers group, schema registry, connect and more

## Features:

#### General
- Works with modern Kafka cluster (1.0+)
- Connection on standard or ssl, sasl cluster
- Multi cluster
#### Topics
- List
- Configurations view
- Partitions view
- ACLS view
- Consumers groups assignments view
- Node leader & assignments view
- Create a topic
- Configure a topic
- Delete a topic
#### Browse Topic datas
- View data, offset, key, timestamp & headers
- Automatic deserializarion of avro message encoded with schema registry
- Configurations view
- Logs view
- Delete a record
- Empty a Topic (Delete all the record from one topic)
- Sort view
- Filter per partitions
- Filter with a starting time
- Filter data with a search string
#### Consumer Groups (only with kafka internal storage, not with old Zookeeper)
- List with lag, topics assignments
- Partitions view & lag
- ACLS view
- Node leader & assignments view
- Display active and pending consumers groups
- Delete a consumer group
- Update consumer group offsets to start / end / timestamp
#### Schema Registry
- List schema
- Create / Update / Delete a schema
- View and delete individual schema version
#### Connect
- List connect definition
- Create / Update / Delete a definition
- Pause / Resume / Restart a definition or a task
#### Nodes
- List
- Configurations view
- Logs view
- Configure a node
#### ACLs
- List principals
- List principals topic & group acls
#### Authentification and Roles
- Read only mode
- BasicHttp with roles per user
- User groups configuration
- Filter topics with regexp for current groups
- Ldap configuration to match AKHQ groups/roles
