# Open WebUI with LiteLLM Setup

This project sets up an Open WebUI interface with LiteLLM as a backend proxy for various AI models. It uses Docker Compose to orchestrate the services.

## Prerequisites

-   Docker and Docker Compose installed on your system
-   API keys for the AI models you want to use

## Configuration

1. Create a `.env` file in the project root with the following content:

    ```ymal
    MASTER_KEY=your_master_key
    ANTHROPIC_API_KEY=your_anthropic_api_key
    OPENAI_API_KEY=your_openai_api_key
    DEEPSEEK_API_KEY=your_deepseek_api_key
    CODESTRAL_API_KEY=your_codestral_api_key
    GROQ_API_KEY=your_groq_api_key
    ```

    Replace `your_*_api_key` with your actual API keys.

2. Ensure the `config.yml` file is present in the project root. This file configures the available models for LiteLLM.

## Usage

1. Start the services:

    ```bash
    docker-compose up -d
    ```

2. Access the Open WebUI interface at `http://localhost:3000`

3. Use the MASTER_KEY as the API key when prompted in the interface.

## Services

-   **Open WebUI**: Runs on port 3000, provides the user interface.
-   **LiteLLM**: Runs on port 4000, acts as a proxy for various AI models.

## Available Models

The following models are configured in `config.yml`:

-   claude-3-5-sonnet (Anthropic)
-   gpt-4o (OpenAI)
-   gpt-4o-mini (OpenAI)
-   deepseek-coder (DeepSeek)
-   deepseek-chat (DeepSeek)
-   codestral (Codestral)
-   groq-llama-3.1-405b (Groq)
-   groq-llama-3.1-70b (Groq)
-   groq-llama-3.1-8b (Groq)

## Security Note

This setup uses environment variables to manage API keys. Ensure that your `.env` file is not committed to version control and is properly secured.

## Troubleshooting

If you encounter any issues, check the Docker logs for each service:
