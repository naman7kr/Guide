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

##### Filtering Data
To filter records, return a boolean value as the return value of the Quick Processor
`return Math.random() < 0.5;`

##### Transforming data
 complete data objects as return values
 filtering and transforming a record can be combined: return false  if the record does not meet the criteria; otherwise, return the modified record.
 `rec.value.celsius = (rec.value.temperature - 32) * 5/9;
return rec;`

#### Base 64 Encoding / Decoding:
Currently, ATOB or BTOA are not supported in the Quick Processor. You can use the following functions instead.

```function b2a(a) {
var c, d, e, f, g, h, i, j, o, b = "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789+/=", k = 0, l = 0, m = "", n = [];
if (!a) return a;
do c = a.charCodeAt(k++), d = a.charCodeAt(k++), e = a.charCodeAt(k++), j = c << 16 | d << 8 | e, 
f = 63 & j >> 18, g = 63 & j >> 12, h = 63 & j >> 6, i = 63 & j, n[l++] = b.charAt(f) + b.charAt(g) + b.charAt(h) + b.charAt(i); while (k < a.length);
return m = n.join(""), o = a.length % 3, (o ? m.slice(0, o - 3) :m) + "===".slice(o || 3);
}


function a2b(a) {
var b, c, d, e = {}, f = 0, g = 0, h = "", i = String.fromCharCode, j = a.length;
for (b = 0; 64 > b; b++) e["ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789+/".charAt(b)] = b;
for (c = 0; j > c; c++) for (b = e[a.charAt(c)], f = (f << 6) + b, g += 6; g >= 8; ) ((d = 255 & f >>> (g -= 8)) || j - 2 > c) && (h += i(d));
return h;
}

rec.value = b2a(rec.value);
return rec;```