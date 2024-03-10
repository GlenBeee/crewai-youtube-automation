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

See [ISSUES.md](./ISSUES.md) for the output, it works through so far then gives an error:

```
Index out of range
```

Perhaps ./tools/youtube_video_search_tool.py is not receiving sufficient data back from the YouTube API

It is difficult to know how we debug this with CrewAI - open to suggestions!