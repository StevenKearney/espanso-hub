# espanso-llm-ask-ai

An Espanso package that enables users to quickly send prompts to a local (e.g. Ollama or LM Studio) or remote LLM API calls (OpenAI standard) and insert the AI-generated response directly into any text field.

## Requirements

- [Espanso](https://espanso.org/) installed and running
- Python 3.9+ installed and available on your system path
- Required Python packages: `openai` and `python-dotenv` (see `requirements.txt`)
- Access to a local LLM (such as [Ollama](https://ollama.com/) or [LM Studio](https://lmstudio.ai/)) or a remote OpenAI compatible API (in this case, you will need to provide your API key in the `.env` file)

## Configuration

Edit the `.env` environment file inside the package directory () to set the `API_KEY`, `BASE_URL`and `MODEL`. Example:

```bash
API_KEY=ollama
BASE_URL=http://localhost:11434/v1
MODEL=llama3.2
```

> NOTE: don't forget to pull the Ollama model first. In the case above, just issue the command:
>
> `ollama pull llama3.2`

## Usage

- Type the Espanso trigger for this package (`:ask:ai`) in any text field.
- Enter your desired AI prompt when asked.
- The AI-generated response will be inserted automatically (this can take several seconds, so choose a small and low latency LLM model).

### Example

Type:
```
:ask:ai
```
Then enter:
```
Summarize the following text: ...
```
Press the "Submit" button or "CTRL + Enter" to send the request. The response from your configured LLM will appear in place.

## Troubleshooting

- Make sure `python` (not `python3`) executable is available globally on your system's PATH environment variable and that the required packages are installed.
- Certain Linux distributions, such as Debian, use only a `python3` executable and don't include a `python` executable or symlink. In this case, you may need to create a symbolic link or run a command like this:
  ```bash
  sudo update-alternatives --install /usr/bin/python python /usr/bin/python3 10
  ```

- Make sure you have the necessary Python packages installed globally, either by running `pip install openai python-dotenv` or by using a command like `sudo apt install python3-openai python3-dotenv`.
- Check that your BASE_URL endpoint, MODEL and API_KEY are correctly set in the `.env` file (located in the Espanso config directory: `%CONFIG%/match/packages/espanso-llm-ask-ai/.env`).
- After sending the request, make sure the cursor doesn’t lose focus and remains blinking at the correct insertion point. If it doesn’t, just click to place it right after the trigger string like this **:ask:ai|**
- Review Espanso logs for errors.

## License

MIT

## Author

Bernhard Enders

## Links

- [Homepage](https://github.com/bgeneto/espanso-llm-ask-ai)
- [Espanso Documentation](https://espanso.org/docs/)