# trading-lab

> Algorithmic trading bot with Go backend and cloud infrastructure via Terraform

![Go](https://img.shields.io/badge/Go-1.21+-blue?logo=go&logoColor=white)
![Terraform](https://img.shields.io/badge/Terraform-IaC-purple?logo=terraform)

---

## Overview

A modular algorithmic trading lab with a **Go backend** and **Terraform-managed cloud infrastructure**. The system is structured around discrete concerns — strategy execution, market data analytics, real-time dashboard, and backtesting simulation — deployed across dev and production environments via Terraform.

---

## Architecture

```
trading-lab/
├── src/
│   ├── cmd/
│   │   ├── bot/          # Main trading bot entry point
│   │   ├── analytics/    # Market data analysis CLI
│   │   ├── dashboard/    # Real-time metrics UI
│   │   └── simulation/   # Backtesting + Monte Carlo
│   └── internal/
│       ├── strategies/   # Trading algorithm implementations
│       ├── analytics/    # Data processing logic
│       ├── dashboard/    # Dashboard rendering
│       └── simulation/   # Simulation engine
└── terraform/
    ├── environments/
    │   ├── dev/          # Development infrastructure
    │   └── prod/         # Production infrastructure
    └── modules/          # Reusable infrastructure modules
```

---

## Components

### Trading Bot (`cmd/bot`)
Core execution engine. Consumes market data, applies strategy logic, and manages position state.

### Analytics (`cmd/analytics` / `internal/analytics`)
Market data ingestion, transformation, and signal generation pipeline.

### Dashboard (`cmd/dashboard` / `internal/dashboard`)
Real-time trading metrics and position monitoring UI.

### Simulation (`cmd/simulation` / `internal/simulation`)
Backtesting engine and Monte Carlo simulation for strategy validation before live deployment.

### Infrastructure (`terraform/`)
Multi-environment Terraform setup (dev/prod) with reusable modules for compute, networking, and storage resources used by the trading stack.

---

## Tech Stack

| Component | Technology |
|-----------|-----------|
| Backend | Go 1.21+ |
| Architecture | Clean architecture (cmd / internal separation) |
| IaC | Terraform (multi-environment) |
| Strategy Engine | Custom Go modules |
| Simulation | Monte Carlo backtesting |

---

## Getting Started

### Build

```bash
cd src
go build ./cmd/bot/...
go build ./cmd/analytics/...
```

### Run Bot

```bash
./bot --config config.yaml
```

### Run Simulation

```bash
./simulation --strategy momentum --period 90d
```

### Deploy Infrastructure

```bash
cd terraform/environments/dev
terraform init && terraform apply
```

---

## Author

**Ash Clements** — Sr. Principal Security Consultant | Infrastructure Automation
[github.com/BadAsh99](https://github.com/BadAsh99)
