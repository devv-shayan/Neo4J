# Use Cases for Graphs

## Graphs Are Everywhere

Graphs aren't just for math! They're widely used across various industries and applications. Neo4j promotes this concept with the idea that "Graphs are Everywhere." They offer a collection of graphgists (graph models) designed by their engineers and community, serving as examples of how graphs can be used in different applications. These can be used as templates or starting points for developing graph-based applications.

## Relationships in E-commerce Systems

Here's a breakdown of the key entities in an e-commerce system and their relationships:

- **Customer**: A person who places an order or rates a product.
- **Order**: The purchase made by a customer. The relationship `:PURCHASED` shows the customer bought a product through an order.
- **Product**: An item the customer buys and may later rate. The `:PRODUCT` relationship shows the connection between an order and the product purchased.

### Key Relationships:

- **Customer → Order (PURCHASED)**: Indicates a customer has placed an order.
- **Order → Product (PRODUCT)**: The order contains one or more products.
- **Customer → Product (RATES)**: After purchasing, the customer might rate the product, with the rating score stored as a property `{rating: 0.0}` in the relationship.

## Use Case in E-commerce: Recommendations and Ratings

By analyzing these relationships, the system can recommend products and track customer ratings:

- **Recommendations**: If many customers purchased Product A and Product B, the system can recommend Product B to others who bought Product A.
- **Product Ratings**: The system tracks how customers rate products, which can influence recommendations or product ranking on the platform.

## E-commerce and Real-Time Recommendations

Traditional e-commerce systems often rely on relational databases (like SQL), which can be cumbersome for tasks like real-time recommendations or dealing with hierarchical data. Here's how graph databases, like Neo4j, solve some of these problems:

### Category Hierarchies:

Finding products in a parent-child category hierarchy is complex with traditional databases, requiring long SQL queries. With Neo4j's Cypher query language, you can retrieve this data efficiently using a short query.

### Cypher Query

```cypher
MATCH (c:Category)-[:HAS_CHILD|HAS_PRODUCT*1..3]->(p:Product)
RETURN p.id, p.title, collect(c.name) AS categories
```
This query finds products in up to 3 levels of subcategories (like Parent → Child → Product) in just a few lines of code.

### "People Who Bought Also Bought" Recommendations:

Relational databases require a lot of batch processing to generate these recommendations. Graph databases excel at this task because they only need to traverse a small part of the overall graph. With Neo4j, instead of querying all customers or orders, you start from one product node, traverse the graph through customers who bought it, and check what else they bought. This approach is much faster.

## Product Ratings Example

Neo4j can also help with calculating product ratings based on the number of purchases or direct ratings from customers. By storing customer interactions in a graph structure, it's easier to pull meaningful insights from the data.

## Summary of Key Concepts

- **Graphs Simplify Relationships**: Traversing data in a graph database is efficient for tasks like recommendations or hierarchy management.
- **Real-Time Recommendations**: Neo4j can easily generate real-time recommendations by starting from a product node and following customer paths.
- **Graphgists**: Neo4j offers graphgists as starting points for developers to explore use cases for graphs in different industries.
