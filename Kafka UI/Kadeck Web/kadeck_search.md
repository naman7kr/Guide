# Kadeck

### Data Browsing

![Data Browsing](https://support.xeotek.com/hc/article_attachments/360018920379/mceclip0.png)

The data browser is divided into three sections: the Streams Browser, Detail View, and the Record List

- Streams Browser -> Kafka topics list
- Record List -> The record list displays records and allows to sort and select records, in order to forward them to another stream, for example.
- Detail View -> The detail view shows all details of a selected record. If your dataset contains structured data, a click on an attribute opens the filter bubble. The filter bubble can be used to quickly filter data records by attribute.

### Search using regular expressions, asterisks or attributes

- Attribute Filters
  ![Attribute Filters](https://support.xeotek.com/hc/article_attachments/360018884600/mceclip1.png)
  In detail view, click on the field and filter
  In the case of structured data (e.g. JSON or Avro), data records can be quickly filtered out using attributes. In this example, a filter is created that filters out data records with a Fahrenheit value of over 30.

- Search and regular expressions
 ![Search using Regex](https://support.xeotek.com/hc/article_attachments/360018924079/mceclip2.png)
The search bar allows you to find records that contain a certain character string or pattern (regex).
##### Regular Expression
To use regular expressions in the search input field, write "regex:" followed by your regular expression.

example: regex:.*Kum.*

##### Asterisk Search
An asterisk (*) is placed at the beginning, at the end, or on both sides of the term, depending on what you are looking for
*Kum*

### Quick Processor
![Quick Processor](https://support.xeotek.com/hc/article_attachments/360018876880/mceclip1.png)


| Attribute | Type | Description |
| ------------- | ------------- | ------------- |
|Value|	any	| The record's decoded value |
|Key|	any |	The record's decoded key |
|Timestamp |	number|	The record's timestamp|
|Topic / Stream|	string|	The stream in which the record was published.|
|Partition / Shard|	number|	The partition or shard in which the record was published.|
|Offset (Apache Kafka only)|	number|	The offset of the record within the stream. (Apache Kafka only)|
|Headers (Apache Kafka only)|	[{  key: string,  value: byte[] }] |	An array containing the headers as objects. The header objects have a key (the name of the header) and a value attribute (the value as a byte array). |

##### State and stateful calculations

A state is saved with the store(any) command. The restore():any command can be used to load the state from the state memory into a variable, for example. To initialize a state memory (e.g. to set an initial value), the command hasStore():boolean can be used to query whether a state already exists.
