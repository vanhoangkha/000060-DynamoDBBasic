---
title : "Naming Rules and Data Types"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 1.4</b> "
---

#### **Naming rules**
- Tables, properties, and other objects in **DynamoDB** must have names.
- Following are the naming rules for DynamoDB:
    + All names must be encoded with ***UTF-8*** and have ***case sensitive***.
    + Table name and index name must be from ***3 to 255 characters*** and can only contain the following characters:
        - a-z
        - A-Z
        - 0-9
        - _(underlined)
        - - (dash line)
        - . (dots)
- The attribute name must be at least one character long, but no longer than 64 KB.
- The following are exceptions. These property names cannot be longer than 255 characters:
    + The key name of the Secondary Index partition.
    + Secondary Index sorts the key names.
    + The name of any user-specified expected properties (applies only to local SecondaryIndexes).
  
#### **Datatypes**
**DynamoDB** supports many different data types for the attributes in the table. They can be classified as follows:
- **Scalar types:** A scalar type can represent exactly one value. Scalar types are **numeric, string, binary, Boolean, and null**.
- **Document Type:** A document type can represent a complex structure with nested properties, such as you will find in a JSON document. The document types are **list** and **map**.
- **Set type:** A set type can represent many scalar values. Set types are **string set, numeric set, and binary set**.