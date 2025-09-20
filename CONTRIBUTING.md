# Contributing to pretty-traceback

Thanks for considering contributing to pretty-traceback! This document outlines the development setup and contribution process.

## Development Setup

### Prerequisites

- [Python 3.8+](https://www.python.org/downloads/)
- [mise](https://mise.jdx.dev/) for Python version management
- [uv](https://docs.astral.sh/uv/) for dependency management

### Getting Started

1. Clone the repository:
   ```bash
   git clone https://github.com/mbarkhau/pretty-traceback.git
   cd pretty-traceback
   ```

2. Install Python and dependencies:
   ```bash
   mise install
   uv sync --all-extras
   ```

## Development Workflow

### Running Tests
```bash
mise run test
# or directly: uv run pytest
```

### Code Quality

Run linting and formatting:
```bash
mise run lint    # Check code quality
mise run format  # Format and auto-fix code
mise run check   # CI-style checks without fixing
```

Individual tools:
```bash
uv run ruff check src/ test/        # Linting
uv run ruff format src/ test/       # Formatting
uv run mypy src/                    # Type checking
```

### Building
```bash
mise run build
# or directly: uv build
```

## Project Structure

```
src/pretty_traceback/    # Main package source
test/                    # Test suite
docs/                    # Documentation and assets
├── screenshots/         # Example images
└── assets/             # Logos and other assets
```

## Making Changes

1. Create a feature branch: `git checkout -b feature-name`
2. Make your changes and add tests if applicable
3. Run the full test suite: `mise run test`
4. Check code quality: `mise run check`
5. Commit your changes with a descriptive message
6. Push and create a pull request

## Code Style

This project uses:
- **ruff** for linting and formatting
- **mypy** for type checking
- **pytest** for testing

All code should pass the checks in `mise run check` before submitting.

## Releasing

This project uses [CalVer](https://calver.org/) versioning (YYYY.BUILD format) with automatic version management via `bumpver`.

## Questions?

Feel free to open an issue for any questions about contributing!