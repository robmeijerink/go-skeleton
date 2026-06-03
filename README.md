# Go Skeleton

A minimalist, container-first boilerplate for starting new Go projects. This template keeps the root directory clean and leverages Docker for all Go operations, meaning you don't even need Go installed locally to start developing.

## Features

* **Zero Local Go Dependency:** All build, test, and run commands execute inside isolated `golang:1.26-alpine` Docker containers.
* **Taskfile Automation:** Simplified command execution with an interactive UI (replaces Makefiles).
* **Hot Reloading:** Pre-configured with Air (`.air.toml`) for fast development cycles.
* **Clean Architecture:** Infrastructure config is neatly tucked away in the `.devcontainer/` directory (also enables one-click Dev Containers).

## Prerequisites

Before generating a project, ensure you have the following installed:

| Tool | Requirement |
| :--- | :--- |
| [Docker](https://docs.docker.com/get-docker/) & Docker Compose | Required |
| [Task](https://taskfile.dev/installation/) | Required |
| [fzf](https://github.com/junegunn/fzf) | Optional (Required for the interactive Task menu) |

*Note: A local Go installation is strictly optional.*

## Getting Started

### 1. Create a New Project
Click the **Use this template** button on GitHub to generate a new repository.

### 2. Clone the Repository

```bash
git clone git@github.com:your-org/your-new-project.git
cd your-new-project
```

### 3. Initialize the Go Module
To keep this skeleton bloat-free, it does not include a `go.mod`. Initialize it using the Dockerized Go environment:

## Available Commands

This template uses `Taskfile.yaml` to manage standard development operations.

Run `task` without any arguments to open the interactive `fzf` search menu, or run specific tasks directly:

| Command               | Description |
| :---                  | :--- |
| `task build`          | Compiles the application into a static binary (`my_app`). |
| `task run`            | Runs `main.go` interactively inside a container. |
| `task test`           | Executes the test suite with the race detector enabled. |
| <code>task&nbsp;get&nbsp;&#8209;&#8209;&nbsp;&lt;pkg&gt;</code>   | Installs a new Go package and runs `go mod tidy` (e.g., `task get -- github.com/gofiber/fiber/v3`). |
| `task tidy`           | Cleans up and verifies module dependencies. |
| `task clean`          | Removes the compiled binary. |

## Project Structure

| File / Directory      | Description |
| :---                  | :--- |
| `main.go`             | The application entry point. |
| `.air.toml`           | Configuration for hot-reloading. |
| `.devcontainer/`      | Dev Container config (`devcontainer.json`) and `docker-compose.yml` for local infrastructure. |
| `.github/`            | CI/CD workflows and `CODEOWNERS`. |
| `Taskfile.yaml`       | Task runner configuration. |

---

This repository serves as the official starting point for projects developed by [Solvalutions](https://solvalutions.com) and [Rob Meijerink](https://robmeijerink.nl).

*&copy;&nbsp;2026 &mdash; Built by Rob Meijerink to accelerate Go development.*
