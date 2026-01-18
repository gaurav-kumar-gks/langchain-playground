## Setup Instructions

### 1. Install Ollama

Ollama allows you to run large language models locally without API keys.

**macOS:**
```bash
brew install ollama
```


### 2. Download the Qwen Model

After installing Ollama, download the Qwen 2.5 7B model:

```bash
# Start Ollama service (if not already running)
ollama serve

# In another terminal, pull the model
ollama pull qwen2.5:7b
```

### 3. Install uv (Python Package Manager)


**macOS:**
```bash
brew install uv
```

### 4. Set Up Python Environment

**Create a new Python project with uv:**
```bash
# Navigate to your project directory
cd langchain-playground

# Create virtual environment and set Python version
uv venv

# Activate the virtual environment
source .venv/bin/activate
```

**Set Python version (if needed):**
```bash
# uv will use the version specified in .python-version
# Or specify explicitly:
uv python install 3.12
```

### 5. Install Dependencies

**Install project dependencies:**
```bash
# Install all dependencies (including dev dependencies)
uv sync

# Installing dependencies only
uv sync --no-dev

# Installing dev dependencies
uv sync --group dev
```

### 6. Set Up Development Tools

#### Ruff (Linter & Formatter)

```bash
# Check for linting issues
uv run ruff check .

# Auto-fix issues
uv run ruff check --fix .

# Format code
uv run ruff format .
```

#### Pre-commit Hooks (Optional)

Pre-commit hooks automatically run Ruff before each commit:

```bash
# Install pre-commit hooks
uv run pre-commit install

# Test hooks manually
uv run pre-commit run --all-files
```


## Running the Project

### 1. Start Ollama Service

Make sure Ollama is running:

```bash
ollama serve
```

### 2. Run the Agent

```bash
source .venv/bin/activate 

python main.py
```
