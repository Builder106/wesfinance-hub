<picture>
  <source media="(prefers-color-scheme: dark)"  srcset="assets/banner-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="assets/banner-light.svg">
  <img alt="WesFinance Hub — Centralized platform for Wesleyan's Econ & Finance community" src="assets/banner-dark.svg">
</picture>

[![CI](https://github.com/yinkavaughan/wesfinance-hub/actions/workflows/ci.yml/badge.svg)](https://github.com/yinkavaughan/wesfinance-hub/actions)
[![Language](https://img.shields.io/badge/typescript-5%2B-blue.svg)](https://www.typescriptlang.org/)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](#license)

## Architecture
```mermaid
sequenceDiagram
    participant Student
    participant Hub
    participant Database
    
    Student->>Hub: Access Hub
    Hub->>Database: Fetch Events & Network
    Database-->>Hub: Return Data
    Hub-->>Student: Display Centralized Portal
```

## Setup
(To be written after architecture decision)

## License
[MIT License](#license)
