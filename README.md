# PMAgent

PMAgent is a Python package that helps developers, data scientist, devops to refactor and modify code using OpenAI/Groq. It reads code from files, interacts with an LLM to generate modifications, and saves changes back to the files. It can create New project with any programming languages. 

Just give your prompt / directory for execution.

## Installation

To install PMAgent:

```bash
pip install PMAgent

# ENVIRONMENT Variables:
# You can use Either GROQ / OPENAI Key ( Mandatory atleast one key)
export OPENAI_API_KEY="sk-"
export GROQ_API_KEY="gsk_"

# Optional Variables - based on your API key
export MODEL=""
export TEMPERATURE=""
export TOP_P=""
export MAX_TOKENS=""

# To Execute:
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
# Provide atleast one key
os.environ["OPENAI_API_KEY"] = "your_key_here"
os.environ["GROQ_API_KEY"] = "your_key_here"

def main():
    # Create an instance of the LLMInteractionManager # all fields are OPTIONAL (Provide at least one key)
    llm_interaction_manager = LLMInteractionManager(
        openai_api_key=os.getenv("OPENAI_API_KEY"), 
        groq_api_key=os.getenv("GROQ_API_KEY"),
        config={
            "model": "llama-3.1-70b-versatile",
            "temperature": 0.5,
            "top_p": 0.9,
            "max_tokens": 4000,
        }
    )

    # Define the message and path you want to use
    user_message = "Fix the code from playground/ folder and rewrite the code in an advanced professional way on the same file"
    path = "playground"

    # Call the interact_with_llm function
    llm_interaction_manager.interact_with_llm(user_message, path=path)

if __name__ == "__main__":
    main()

```