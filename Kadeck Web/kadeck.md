# Xeoteck Kadeck
> KaDeck is the advanced data-centric Apache Kafka/Amazon Kinesis monitoring solution

### System Requirements
OS: 
- Windows with support for java 11+
- Linux distribution 64-bit with support for Java 11+
- Mac OS with support for Java 11+

Container Requirements:
- 64-bit operating system
- min. 8GB of free RAM *
- 1 GB of disk space

Kafka Version: 
- KaDeck was tested with Apache Kafka 1.0+ and may work with older versions, but we do not recommend using any version of Kafka below 1.0 in a production environment

### Architecture
![Architecture](https://support.xeotek.com/hc/article_attachments/360019264200/mceclip0.png)

### Configuration List

You can configure KaDeck by supplying the following environment variables:

| Variable name  | Example value | Description |
| ------------- | ------------- | ------------- |
| secret |	password |	Required. Your secret authentication code. |
| teamid |	myteam.abecede	| Required. Your team id. |
|init_with_userid |	mycustomuserid | The user id of the first admin user. Defaults to admin. The default password admin is not affected. |
|port |	80 |	The port through which the web UI of KaDeck Enterprise will be accessible. |
| keystore_path | /your/path |	SSL: The absolute path to your keystore. |
| keystore_pass | password |	SSL: The password of your keystore. |
| keystore_alias |	alias |	SSL: The keystore alias. |
| db_url |	jdbc:h2:address | 	The JDBC URL of your SQL database. Currently, PostgreSQL and H2 are supported. If not supplied, a database is created in the container (not recommended in production). |
| db_username |	username |	The username with permissions to create tables and read/write values to it. |
| db_password |	password |	The password for your user. |
| sync_max_interval_mins |	120 |	KaDeck Web only. The synchronization interval for pulling new data from the Xeotek Uplink server. |
| loglevel |	INFO |	The log level of KaDeck. Default: WARN |

### Data Analysis and Filters
- Filtering using data object attributes (json and avro)
- Complex queries with JavaScript
- Transform records on the fly
- Search by time and time windows
- Search for key and values

### Data Routing and Export
- Correct erroneous data sets
- Send data sets to a stream
- Export data sets, e.g. as CSV

### Data Transformation

- Use JavaScript to filter and transform data
- Stateful calculations supported (e.g., averages, grouping)
- Runs in real-time

### Find relevant data faster

- Save your individual transformations, filters and view settings
- Share them with your team
- Add attributes as columns in your reports
- Sort records by attributes

### Codecs & auto-detection
##### For consumption and ingestion:
- JSON Codec
- Avro Codec
- String Codec
- Integer Codec
- Float Codec
- Long Codec
- Double Codec

##### For consumption only:
- Avro Embedded Codec
- Avro Topic Record Strategy Codec
- Avro Record Strategy Codec
- CSV Codec for single and multi-line CSV

### Connectivity and security

- SSL with optional custom keystore
- SASL with SSL
- SASL with plain, gssapi and scram

##### Schema Registry security:
- Basic auth (user)
- Bearer (token)

### Data Ingestion
- Ingest multiple records at once
- Send records from one topic to another
- Support for record headers
- Intuitive UI and additional JSON view
- Use existing records as templates
- Many supported codecs
- Extendable using own custom codecs

### More features

- Embedded Apache Kafka broker
- FlowView enables end-to-end monitoring of your data flow
- Create and delete topics
- Export single and multiple records
- Test Java applications with live data utilizing our Codecs API
- Seek to offsets across partitions
- Seek to offsets by timestamp

