# Product Design

## Objective

**Credit Card Optimizer** aims to be a customizable credit card search & recommendation engine that help users optimize credit card benefits.

## Background

As online and in-store promotions has become more common, there are many utilities apps that help users search available coupons or recommend coupons

However, although almost every transaction goes through credit cards, the benefits that comes with the payment method itself is often overlooked.

With the correct combination of credit cards and strategies, the reward can be significantly optimized.

This project aims to help user manage credit cards and optimize reward with algorithms.

## Design

```mermaid
graph TD
    CLIENTS[Clients: mobile app, web app, and CLI, etc] -- REST API --- SERVER[Server: core logic]
    CLIENTS -- Protobuf code generation --- COMMON_CONCETPS
    SERVER -- Protobuf code generation --- COMMON_CONCETPS
    SERVER --> DEPLOY_VENDOR[Deploy vendor: Vercel]
    SERVER --> SERVICE_PROVIDER[Service provider vendor: Firebase]
```
