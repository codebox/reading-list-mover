# Reading List Mover

Copy bookmarks between Instapaper, Readability, Pocket, Pinboard, Delicious and Diigo

Here's a small Python library to [copy bookmarks between a number of online bookmarking/reading list services][source]. The library supports [Instapaper][], [Readability][], [Pocket][] (formerly ReadItLater), [Pinboard][], [Delicious][] and [Diigo][].

To use the library you will need to populate your copy of the [config.txt][] file with the details of your accounts on the services that you are going to use. In the case of Readability, Pocket, Instapaper and Diigo you will also need to apply for an API key:

- [Readability API key](http://help.readability.com/customer/portal/articles/267466-i%E2%80%99m-a-developer-how-can-i-get-an-api-key-)
- [Pocket API key](http://getpocket.com/api/signup/)
- [Instapaper API key](http://www.instapaper.com/main/request_oauth_consumer_token)
- [Diigo API key](http://www.diigo.com/api_keys/new/)

You will also need to have the [oauth2][] Python library installed on your system.

Here's an example showing how to copy all your bookmarks from one service to another:

## Copy from Pocket to Readability ##

```python
# Copy all bookmarks from Pocket to Readability
pocket = buildPocket()
readability = buildReadability()

for b in pocket.getBookmarks():
    readability.addBookmark(b)
```

You can also use the library to export a list of your bookmarks for use as a backup:

## Export all Delicious bookmarks

```python
# Print out all bookmarks from Delicious
delicious = buildDelicious()

for b in delicious.getBookmarks():
    print b['title'] + ': ' + b['url']
```

[source]: https://github.com/codebox/reading-list-mover
[Instapaper]: http://www.instapaper.com/
[Readability]: https://www.readability.com/
[Pocket]: http://getpocket.com/
[Pinboard]: http://pinboard.in/
[Delicious]: http://delicious.com/
[Diigo]: http://diigo.com/
[config.txt]: https://github.com/codebox/reading-list-mover/blob/master/config.txt
[oauth2]: https://github.com/simplegeo/python-oauth2
