Wallet Microservice

This project is a backend microservice designed to simulate a basic cryptocurrency wallet system. It enables users to create wallets, deposit and withdraw funds, and view transaction history. The service is built using idiomatic Go, gRPC, PostgreSQL, and Docker. It's designed to reflect real-world backend engineering practices as used in fintech and crypto companies like Luno.

Features

Create wallets tied to a user ID

Deposit and withdraw funds with safety checks

Query current wallet balances

List transaction history per wallet

Transactional data integrity

Fully containerized with Docker

Clean and idiomatic Go project structure

Easily extensible for streaming, caching, and authentication

Technologies Used

Go 1.24+

gRPC for service communication

PostgreSQL for persistent storage

Docker + Docker Compose

Protocol Buffers for service contracts

Project Structure

.
├── cmd/                    # Entrypoints for services (server)
│   └── server/
│       ├── Dockerfile
│       └── main.go
├── internal/              # Application logic
│   ├── server/            # gRPC server logic & DB connection
│   ├── models/            # Domain models
│   └── test/              # Unit and integration tests
├── proto/                 # .proto definitions and generated code
├── docker/                # DB init scripts
├── docker-compose.yml     # Service orchestration
├── go.mod / go.sum        # Go module files
└── README.md

Usage

Prerequisites

Docker and Docker Compose installed

Run the Application

docker-compose up --build

Proto Compilation

To regenerate gRPC code after editing proto/wallet.proto:

protoc \
  --go_out=. \
  --go-grpc_out=. \
  --go_opt=paths=source_relative \
  --go-grpc_opt=paths=source_relative \
  proto/wallet.proto

API Overview

RPC

Description

CreateWallet(userId)

Create a new wallet

Deposit(walletId, amt)

Add funds to a wallet

Withdraw(walletId, amt)

Subtract funds (no overdraft)

GetBalance(walletId)

Get current wallet balance

ListTransactions()

Get list of past transactions

License

MIT

This project is built for educational purposes to strengthen backend engineering skills for fintech domains. Contributions and feedback are welcome!
