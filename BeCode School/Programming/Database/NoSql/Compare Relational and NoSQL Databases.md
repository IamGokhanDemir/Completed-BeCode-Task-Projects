---
sticker: lucide//database
---
## Relational and NoSQL Databases

### 📊 **Relational Databases** 📊

Relational databases have been the go-to choice for businesses for years. They resemble our connections with others, with tables interconnected in a database.

Think of a relational database table as a 📑 spreadsheet tab 📑. Each row holds specific information like a book title, and columns hold related details like author, publication date, and more.

This method prevents redundancy and ensures data is stored in one spot. Changes are consistent and updates are easy.

### 📝 **NoSQL in Relation to Relational Databases** 📝

Ever heard of **Not Only SQL (NoSQL)**? It's a newer type of database, including names like Couchbase, MongoDB, and Cassandra.

NoSQL databases can be categorized into four types:

1. **Column**
2. **Graph**
3. **Key-value**
4. **Document**

Let's explore them briefly.

1. **Column:** Timestamp-based, used in distributed environments. Example: Cassandra.
2. **Graph:** Nodes and edges for data and relationships. Example: Neo4j.
3. **Key-value:** Uses dictionary-like structure. Example: Oracle NoSQL.
4. **Document:** Stores object details together. Example: Couchbase.

![Comparison](https://user.oc-static.com/upload/2019/07/05/15623398368289_SQL%20vs%20NoSQL.png)
### 🔄 **SQL vs. NoSQL** 🔄

Relational databases use **SQL** for structured querying. They're highly structured, using predefined tables for scalability.

**NoSQL** databases are dynamic, without a fixed structure. They're great for unstructured data collection.

**NoSQL** is specialized and serves specific needs, like the document store model for car sales tracking:

- Dealerships use an app for recent purchases, saving data usage.
- Relational databases manage updated info.
- NoSQL handles historical data for better insights.

As tech evolves, NoSQL complements, not replaces, relational databases.

### 🚗 **Relational Databases Explained** 🚗

Relational databases store entity details and related records. Duplication is minimized, changes are efficient.

Example: A bookstore stores book, author, and purchase data. Separate tables for each entity, e.g., Books and Authors.

![relation database](https://user.oc-static.com/upload/2019/05/23/15586279607157_Logical%201c2b.png)
### 🧐 **Entities and Attributes** 🧐

An **entity** is anything describable, like a person. Attributes define entities' qualities. In databases, attributes become fields in tables.

For vehicles, color could be an attribute. For restaurants, postal code.

Attributes are small and specific; a complete address breaks into components.

![entities](https://user.oc-static.com/upload/2019/05/31/15593113015604_Two%20tables.png)
### ➗ **Entity Relationships** ➗

Entities relate through primary and foreign keys. Diagrams like Entity Relationship Diagrams (ERDs) show these connections.

Relational databases thrive on related tables for meaningful data retrieval.

![relationships](https://user.oc-static.com/upload/2019/05/31/15593117788003_Big%20ERD.png)
## 📝 **Practice with Multiple Choice Questions** 📝

1. Which type of NoSQL database uses a timestamp to differentiate between valid and old values?
   - [ ] Graph
   - [x] Column
   - [ ] Key-value
   - [ ] Document

2. What is the purpose of Entity Relationship Diagrams (ERDs)?
   - [ ] Display colorful graphics in databases
   - [ ] Explain primary colors in NoSQL databases
   - [x] Show relationships between tables
   - [ ] Describe physical attributes of entities

3. What is the key difference between SQL and NoSQL databases?
   - [x] SQL databases are structured, while NoSQL databases are dynamic
   - [ ] SQL databases are only used in web applications
   - [ ] SQL databases can't handle unstructured data
   - [ ] NoSQL databases use SQL for querying

4. In a relational database, how are attributes related to entities?
   - [ ] Attributes are completely unrelated to entities
   - [x] Attributes become fields within tables
   - [ ] Attributes are stored in separate databases
   - [ ] Attributes are used to define relationships

5. Why do NoSQL databases play an important role alongside relational databases?
   - [ ] NoSQL databases replace relational databases entirely
   - [x] NoSQL databases cater to specific needs and unstructured data
   - [ ] NoSQL databases are more cost-effective
   - [ ] NoSQL databases use a structured querying language

**Answers:**
1. ✔️ Column
2. ✔️ Show relationships between tables
3. ✔️ SQL databases are structured, while NoSQL databases are dynamic
4. ✔️ Attributes become fields within tables
5. ✔️ NoSQL databases cater to specific needs and unstructured data