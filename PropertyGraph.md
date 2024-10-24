# Neo4j Property Graph Overview

A **Property Graph** in Neo4j is a data model that consists of four main components: **nodes**, **relationships**, **labels**, and **properties**. These components are used to structure and query data in a flexible, connected manner. Here's a breakdown:

---

## Neo4j Graph Elements Overview

### Nodes:
- Represent entities (e.g., people, companies, objects).
- In the graph, each node can have **labels** and **properties**.
- In the example: **Michael**, **Sarah**, and **Graph Inc** are nodes.

### Labels:
- Used to categorize nodes into groups.
- A node can have zero, one, or many labels.
- Labels help start queries and filter data.

#### Example labels:
- **Person**, **Male**, **Female**, **Employee**, **Company**.

### Properties:
- **Key-value pairs** that provide additional details about nodes and relationships.
- Properties can be single values or lists.

#### Example properties for nodes:
- **Michael**: `firstName: Michael`, `lastName: Faraday`, `born: 1791-09-22`.
- **Sarah**: `firstName: Sarah`, `lastName: Faraday`, `maidenName: Barnard`.
- **Graph Inc**: `name: Graph Inc`, `city: London`, `numEmployees: 56`, `dba: ['Graph Incorporated', 'GI']`.

---

## Key Concepts for Querying

### Labels:
- Useful for filtering nodes in queries.
- Example: `MATCH (p:Person)` will find all nodes labeled as **Person**.

### Properties:
- Provide specific information.
- Can be queried using key-value pairs.
- Example: `MATCH (m:Person {firstName: "Michael"})` will find the node where first name is **Michael**.

### Relationships:
- Define how two nodes are connected.
- Relationships must have a **type** (e.g., **MARRIED_TO**, **WORKS_AT**).
- Can be traversed in either direction or queried without considering direction.

#### Example:
`MATCH (m:Person)-[:MARRIED_TO]->(s:Person)` will find married pairs.

---

### Properties on Relationships:
- Add extra details to relationships.
- Example: `MATCH (m:Person)-[r:MARRIED_TO]->(s:Person) RETURN r.date` can return the marriage date if the property exists.

---

## Neo4j Graph Design Principles

- **Nodes** are entities.
- **Labels** categorize nodes for efficient querying.
- **Relationships** define how nodes are connected, with directions and types.
- **Properties** provide detailed data for both nodes and relationships.

---

### Relationships:
- Show how nodes are connected.
- Every relationship must have a **direction** and a **type**.

#### Example relationships:
- **MARRIED_TO**: Michael is married to Sarah.
- **WORKS_AT**: Michael works at Graph Inc.

Relationships can also have **properties**, like marriage date or job role.

---

