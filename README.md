# Relay

A personal AI server for creating and managing custom AI workflows and agents. Built with FastAPI and designed to be self-hosted on a Linux VPS via Coolify.

## Overview

Relay is an open-source personal AI orchestration platform that enables you to:

- Create custom AI workflows tailored to your needs
- Build and deploy AI agents for various tasks
- Integrate multiple AI services and APIs
- Manage and monitor your AI workflows from a centralized location
- Self-host with complete control over your data and processes

## Features

- **FastAPI Backend**: High-performance, modern Python web framework
- **Modular Architecture**: Organized structure for agents, workflows, and services
- **Self-Hosted**: Deploy on your own infrastructure via Coolify
- **Extensible**: Easy to add new AI integrations and custom workflows
- **API-First Design**: RESTful API for easy integration with other tools

## Prerequisites

- Python 3.13+
- [uv](https://github.com/astral-sh/uv) package manager
- Linux VPS (for deployment)
- [Coolify](https://coolify.io/) (for deployment)

## Installation

### Local Development

1. Clone the repository:
```bash
git clone <your-repo-url>
cd relay
```

2. Install dependencies using uv:
```bash
uv sync
```

3. Run the development server:
```bash
uv run uvicorn main:app --reload
```

The API will be available at `http://localhost:8000`

## Project Structure

```
relay/
├── main.py              # Main FastAPI application entry point
├── app/
│   ├── api/            # API routes and endpoints
│   ├── models/         # Data models and schemas
│   └── services/       # Business logic and AI integrations
├── pyproject.toml      # Project dependencies and configuration
└── uv.lock            # Dependency lock file
```

## Deployment

### Deploying with Coolify

1. Push your code to a Git repository (GitHub, GitLab, etc.)

2. In Coolify:
   - Create a new application
   - Connect your Git repository
   - Set the build command: `uv sync`
   - Set the start command: `uv run uvicorn main:app --host 0.0.0.0 --port 8000`
   - Configure environment variables as needed

3. Deploy and monitor via the Coolify dashboard

### Environment Variables

Configure the following environment variables in your deployment:

```bash
# Add your environment variables here
# Example:
# OPENAI_API_KEY=your_api_key
# DATABASE_URL=your_database_url
```

## API Documentation

Once the server is running, visit:
- Swagger UI: `http://localhost:8000/docs`
- ReDoc: `http://localhost:8000/redoc`

## Development

### Adding New Workflows

1. Create a new module in `app/services/`
2. Define your workflow logic
3. Add API endpoints in `app/api/`
4. Register routes in `main.py`

### Adding New Agents

1. Create agent definitions in `app/models/`
2. Implement agent logic in `app/services/`
3. Expose agent endpoints via `app/api/`

## Contributing

This is a personal project, but contributions are welcome! Feel free to:

- Report bugs
- Suggest features
- Submit pull requests

## License

MIT License - see [LICENSE](LICENSE) for details

## Acknowledgments

Built with:
- [FastAPI](https://fastapi.tiangolo.com/)
- [uv](https://github.com/astral-sh/uv)
- [Coolify](https://coolify.io/)
