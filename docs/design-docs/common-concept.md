# Common Concept

## Objective

Avoid repetitive declarations of common concepts across various systems.

## Design

```mermaid
graph TD
    subgraph CREDIT_CARD_GROUP
    CREDIT_CARD[Credit Card] --> CREDIT_CARD_METADATA[Metadata]
    CREDIT_CARD --> PROMOTION_LIST[List of promotions]
    end
    PROMOTION_LIST --> PROMOTION[Promotion]
    subgraph PROMOTION_GROUP
    PROMOTION --> PROMOTION_METADATA[Metadata]
    PROMOTION --> CATEGORY_LIST[List of categories]
    end
    CATEGORY_LIST --> CATEGORY
    subgraph CATEGORY_GROUP
    CATEGORY --> STORE_LIST[List of stores]
    CATEGORY --> CATEGORY_METADATA[Metadata]
    end
    STORE_LIST --> STORE
    subgraph STORE_GROUP
    STORE --> STORE_METADATA[Metadata]
    end
```

### Credit Card

The `CreditCard` concept represents all the information about a single credit card.

### Promotion

The `Promotion` concept represents all the information about a single promotion of a credit card.

### Category

The `Category` concept represents a type of stores.

### Store

The `Store` concept represents a specific merchant or shop.
