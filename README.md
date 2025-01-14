# youtube_search

Python module (updated from [#OG42](https://github.com/joetats/youtube_search/pull/42) for searching for youtube videos to avoid using their heavily rate-limited API

To avoid using the API, this uses the form on the youtube homepage and scrapes the resulting page.

## Example

For a basic search (and all of the current functionality), you can use the search tool as follows:

```python -m pip install 'youtube-search @ git+https://github.com/letruxux/youtube_search_updated'```

```python
# Synchronous version
from youtube_search import YoutubeSearch, AsyncYoutubeSearch

search = YoutubeSearch('search terms', max_results=10).fetch()
results_list = search.list()
results_json_string = search.json_string()
print(results_list) # Return inform of list
print(results_json_string) # Return inform of json string

# Asynchronous version
async def main():
    search=await AsyncYoutubeSearch('search terms', max_results=10).fetch()
    results_list = search.list()
    results_json_string = search.json_string()
    print(results_list) # Return inform of list
    print(results_json_string) # Return inform of json string

asyncio.run(main())

```
