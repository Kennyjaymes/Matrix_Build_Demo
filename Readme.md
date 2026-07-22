# 🧪 Matrix Build Demo

A demonstration project showcasing **GitHub Actions Matrix Builds**. This repository demonstrates how to test a Node.js application across multiple operating systems and Node.js runtime versions concurrently.

---

## 📋 Table of Contents
- [Overview](#-overview)
- [Project Structure](#-project-structure)
- [GitHub Actions Matrix Configuration](#-github-actions-matrix-configuration)
- [Local Development](#-local-development)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Running Tests](#running-tests)
- [License](#-license)

---

## 🔍 Overview

This project implements a simple math module exporting an `add` function, with unit tests powered by [Jest](https://jestjs.io/). The core focus is demonstrating GitHub Actions workflows running across multiple operating systems and Node.js versions (9 total environment combinations) to guarantee cross-compatibility.

---

## 📁 Project Structure

```text
Matrix_Build_Demo/
├── .github/
│   └── workflows/
│       └── matrix-build.yml  # GitHub Actions workflow configuration
├── tests/
│   └── add.test.js           # Unit tests
├── index.js                  # Core source code (add function)
├── package.json              # Project dependencies & scripts
├── README.md                 # Project documentation
└── .gitignore                # Git ignored files
```

---

## ⚙️ GitHub Actions Matrix Configuration

The workflow is defined in [.github/workflows/matrix-build.yml](.github/workflows/matrix-build.yml). It triggers automatically on:
- `push` events to the `main` branch.
- `pull_request` events to the `main` branch.

### Matrix Parameters

| Dimension | Target Environments / Versions |
| :--- | :--- |
| **Operating Systems** | `ubuntu-latest`, `windows-latest`, `macos-latest` |
| **Node.js Versions** | `18`, `20`, `22` |

> [!NOTE]
> This 3x3 matrix configures a total of **9 parallel jobs** executing simultaneously on GitHub hosted runners to verify compatibility.

---

## 💻 Local Development

### Prerequisites

Before running locally, ensure you have the following installed:
- [Node.js](https://nodejs.org/) (Version 18 or higher recommended)
- npm (comes bundled with Node.js)

### Installation

Clone the repository and install the developer dependencies:

```bash
npm install
```

### Running Tests

Execute the Jest test suite:

```bash
npm test
```

---

## 📄 License

This project is licensed under the [ISC License](https://opensource.org/licenses/ISC).
