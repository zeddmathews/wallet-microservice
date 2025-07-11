💸 Wallet Microservice

A backend microservice for simulating basic cryptocurrency wallet functionality using Go, gRPC, PostgreSQL, and Docker.

📌 Features

🏦 Create wallets tied to user IDs

💰 Deposit and withdraw funds with transactional safety

📊 Query wallet balances

📜 View transaction history

🔒 ACID-compliant operations

🐳 Fully containerized with Docker

🧹 Idiomatic Go structure

🔧 Easily extensible (caching, streaming, auth)

🛠️ Technologies Used

Go 1.24+

gRPC for fast communication

Protocol Buffers for typed contracts

PostgreSQL for persistent storage

Docker & Docker Compose for containerized setup

📁 Project Structure

.
├── cmd/                    # Entrypoints (e.g., gRPC server)
│   └── server/
│       ├── Dockerfile
│       └── main.go
├── internal/              # Application logic
│   ├── server/            # gRPC server logic & DB
│   ├── models/            # Domain models
│   └── test/              # Unit & integration tests
├── proto/                 # .proto files + generated gRPC code
├── docker/                # DB init scripts (SQL)
├── docker-compose.yml     # Multi-container setup
├── go.mod / go.sum        # Go dependencies
└── README.md

🚀 Usage

✅ Prerequisites

Docker + Docker Compose

🔧 Start the App

docker-compose up --build

📦 Generate Proto Files

protoc \
  --go_out=. \
  --go-grpc_out=. \
  --go_opt=paths=source_relative \
  --go-grpc_opt=paths=source_relative \
  proto/wallet.proto

🔌 gRPC API Overview

RPC

Description

CreateWallet(userId)

Create a wallet for a user

Deposit(walletId, amt)

Add funds to the wallet

Withdraw(walletId, amt)

Withdraw funds (safe only)

GetBalance(walletId)

Check wallet balance

ListTransactions()

View historical transactions

📄 License

MIT

This project is intended for educational use to sharpen real-world backend skills, especially for fintech and crypto environments.

📬 Feedback or contributions? Open a pull request or file an issue!

