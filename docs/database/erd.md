# Entity Relationship Diagram

```mermaid
erDiagram
    USERS ||--o{ ORDERS : places
    ORDERS ||--|{ ORDER_ITEMS : contains
    USERS {
        int id
        string username
        string email
    }
    ORDERS {
        int id
        int user_id
        date order_date
    }
    ORDER_ITEMS {
        int id
        int order_id
        string product_name
        decimal price
    }
```

## Entity Descriptions
Description of each entity and their relationships...
