# Azure Echo App

This project uses the **Azure Functions Python v2 programming model**. All functions are defined in a single `function_app.py` file.

## Prerequisites

- [Python 3.8+](https://www.python.org/downloads/) (recommend 3.12 or newer)
- [Node.js](https://nodejs.org/) (for Azure Functions Core Tools)
- [Azure Functions Core Tools v4](https://learn.microsoft.com/azure/azure-functions/functions-run-local)
- [Azure CLI (optional)](https://docs.microsoft.com/cli/azure/install-azure-cli)
- [Visual Studio Code](https://code.visualstudio.com/) with the [Azure Functions extension](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-azurefunctions)

## Setup Instructions

1. **Clone the repository**  
   ```sh
   git clone <your-repo-url>
   cd azure-echo-app
   ```

2. **Create and activate a virtual environment**  
   ```sh
   py -3.12 -m venv .venv
   .\.venv\Scripts\activate
   ```

3. **Install dependencies**  
   ```sh
   pip install -r requirements.txt
   ```

4. **Install Azure Functions Core Tools**  
   ```sh
   npm install -g azure-functions-core-tools@4 --unsafe-perm true
   ```

5. **(Optional) Install the Azure Functions VS Code extension**  
   - Open VS Code, go to Extensions, and search for "Azure Functions".

## Running the Function Locally

1. **Start the Azure Functions host**  
   ```sh
   func start
   ```

2. **Test the HTTP Trigger**  
   - Use a tool like [curl](https://curl.se/) or [Postman](https://www.postman.com/) to send a request:
     ```sh
     curl "http://localhost:7071/api/EchoFunction?name=YourName"
     ```

## Project Structure

```
azure-echo-app/
│   function_app.py      # Main entry point for all functions (v2 model)
│   requirements.txt     # Python dependencies
│   host.json            # Azure Functions host configuration
│   local.settings.json  # Local development settings (not for production)
│   README.md
│   .venv/               # Python virtual environment (not committed)
```

## Notes

- This project uses the **v2 programming model** for Azure Functions in Python. There are no per-function folders or `function.json` files.
- All functions are defined and registered in `function_app.py` using decorators.
- For more information, see the [Azure Functions Python v2 docs](https://learn.microsoft.com/azure/azure-functions/functions-reference-python?tabs=asgi%2Capplication-level&pivots=python-mode-v2).
