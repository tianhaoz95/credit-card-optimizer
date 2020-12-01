# Common Concept

## Objective

Avoid repetitive declarations of common concepts across various systems.

## Design

### Overview

```mermaid
graph TD
    subgraph USER_GROUP[User]
      USER --> USER_METADATA[Metadata]
      USER --> WALLET_LIST[List of wallets]
      USER --> CREDIT_CARD_LIST[List of credit cards]
      USER --> PROMOTION_LIST[List of promotions]
      USER --> CATEGORY_LIST[List of categories]
      USER --> STORE_LIST[List of stores]
    end

    WALLET_LIST --> WALLET[Wallet]
    PROMOTION_LIST --- PROMOTION_ID_LIST
    CATEGORY_LIST --- CATEGORY_ID_LIST
    STORE_LIST --- STORE_ID_LIST
    CREDIT_CARD_LIST --- CREDIT_CARD[Credit Card]

    subgraph WALLET_GROUP[Wallet]
      WALLET --> WALLET_METADATA[Metadata]
      WALLET --> CREDIT_CARD_ID_LIST[List of credit card identifiers]
    end

    CREDIT_CARD_ID_LIST -.-> CREDIT_CARD

    subgraph CREDIT_CARD_GROUP[Credit Card]
      CREDIT_CARD --> CREDIT_CARD_METADATA[Metadata]
      CREDIT_CARD --> PROMOTION_ID_LIST[List of promotion identifiers]
    end

    PROMOTION_ID_LIST -.-> PROMOTION[Promotion]

    subgraph PROMOTION_GROUP[Promotion]
      PROMOTION --> PROMOTION_METADATA[Metadata]
      PROMOTION --> CATEGORY_ID_LIST[List of category identifiers]
    end

    CATEGORY_ID_LIST -.-> CATEGORY

    subgraph CATEGORY_GROUP[Category]
      CATEGORY --> STORE_ID_LIST[List of store identifiers]
      CATEGORY --> CATEGORY_METADATA[Metadata]
    end

    STORE_ID_LIST -.-> STORE

    subgraph STORE_GROUP[Store]
      STORE --> STORE_METADATA[Metadata]
      STORE_METADATA --> TEMPLATE_IDS[List of tempalte identifiers]
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
