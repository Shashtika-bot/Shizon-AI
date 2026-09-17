# Shizon AI - High-Level Design

## 1. System Overview

Shizon AI follows a client-server architecture.

The React frontend communicates with the Node.js and Express backend through REST APIs. The backend manages application logic and communicates with MongoDB, PostgreSQL, and the LLM API.

## 2. Architecture

```text
                    ┌─────────────────┐
                    │      User       │
                    └────────┬────────┘
                             │
                             ▼
                    ┌─────────────────┐
                    │ React Frontend  │
                    └────────┬────────┘
                             │
                       REST API
                             │
                             ▼
                    ┌─────────────────┐
                    │ Node.js +       │
                    │ Express Backend  │
                    └───┬─────┬────┬──┘
                        │     │    │
              ┌─────────┘     │    └──────────┐
              ▼               ▼               ▼
        ┌──────────┐   ┌────────────┐   ┌──────────┐
        │ MongoDB  │   │ PostgreSQL │   │ LLM API  │
        └──────────┘   └────────────┘   └──────────┘