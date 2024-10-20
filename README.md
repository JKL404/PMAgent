# PMAgent

PMAgent is a Python package that helps developers refactor and modify code using OpenAI. It reads code from files, interacts with an LLM to generate modifications, and saves changes back to the files.

## Installation

To install PMAgent:

```bash
pip install PMAgent

export OPENAI_API_KEY="sk-"

pmagent "Fix the code from playground folder" playground

# pmagent <UserPrompt> <directorytoexecute>

```
#### Put API KEY ON ENV: OPENAI_API_KEY


## Examples

### Bash Terminal Syntax
```bash
pmagent <UserPrompt> <directorytoexecute>
```
### Use Case:
```bash
pmagent "Create a webpage for a clothing store, put some random cloth images from online free images for products and add an add-to-cart button, i have create folder web-page" web-page

pmagent "write a data analyis code on anaylis.ipynb file to do data analyiss on data from data-analysis folder" data-analysis
```


### Python Syntax:
```python

# another_script.py
import os
from pmagent import LLMInteractionManager

# Make sure the environment variable is set for the API key
os.environ["OPENAI_API_KEY"] = "your_openai_api_key_here"

def main():
    # Create an instance of the LLMInteractionManager
    llm_interaction_manager = LLMInteractionManager(api_key=os.getenv("OPENAI_API_KEY"))

    # Define the message and path you want to use
    user_message = "Fix the code from playground/ folder and rewrite the code in an advanced professional way on the same file"
    path = "playground"

    # Call the interact_with_llm function
    llm_interaction_manager.interact_with_llm(user_message, path=path)

if __name__ == "__main__":
    main()

```
