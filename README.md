# Introduction

Based on youtube video https://www.youtube.com/watch?v=OumQe3zotGU

Modified to use local LLM (Ollama)

Added more instructions on YouTube API setup and probable error along with resolution


> poetry install --no-root
> poetry shell

> python main.py 

# Setup Google YouTube API

Create API key at https://console.cloud.google.com/ 
If you havent got an account, create one now
Then create new project - CrewAI-Youtube
Select your project once it has created
Search credentials - Credentials - APIs and Service
Create API key and save in .env file as YOUTUBE_API_KEY=YOUR API KEY

## Potential Google API Error

If you get the following error, there is a solution...

It seems we encountered an unexpected error while trying to use the tool. This was the error: 403 Client Error: Forbidden for url: https://www.googleapis.com/youtube/v3/search?part=snippet&q=CrewAI+for+YouTube+automation&maxResults=description&maxResults=type&type=video&key=AIzaSyDIAZwPo21r2067CwwBgEI3LR0MgHvufdk

Open the url above and it will provide a link similar to this:
    https://console.developers.google.com/apis/api/youtube.googleapis.com/overview?project=12783475893

That should allow you to enable the YOUTUBE API

# Issues

1. Unresolved issue to work out:

> Entering new CrewAgentExecutor chain...
Use Tool: Search YouTube Videos
Keyword: "Automating Tasks Using CrewAI" 

Failed to convert text into a pydantic model due to the following error: Invalid json output: {
    "tool_name": "Search YouTube Videos",
    "arguments": {
        "keyword": "Automating Tasks Using CrewAI",
        "max_results": int (default: 10) // or any reasonable maximum result limit
    }
}
