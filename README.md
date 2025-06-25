# Run and deploy your AI Studio app

This contains everything you need to run your app locally.

## Run Locally

**Prerequisites:**
*   Node.js
*   Ollama installed and running
*   Llama 3 model pulled via Ollama (e.g., `ollama pull llama3:8b`)

1.  Install dependencies:
    `npm install`
2.  Set the `LLAMA_API_ENDPOINT` in a `.env` file (e.g., `.env.local`) to your local Ollama API endpoint.
    Example: `LLAMA_API_ENDPOINT="http://localhost:11434/api/generate"`
3.  The `LLAMA_API_KEY` environment variable is **not required** for local Ollama setups and can be omitted from your `.env` file or left blank.
4.  Run the app:
    `npm run dev`

**Important for Local Ollama (Llama 3) Integration:**
The application is now configured to use a Llama 3 model (specifically `llama3:8b` by default in the code) via your local Ollama instance.
- Ensure your Ollama application is running.
- The `LLAMA_API_ENDPOINT` must point to your Ollama `/api/generate` endpoint.
- The `aiService.ts` handles sending the correct payload to Ollama, including specifying the model and requesting JSON format.
- The service will attempt to parse the JSON response from Ollama. The prompts are designed to instruct Llama 3 to output clean JSON.
