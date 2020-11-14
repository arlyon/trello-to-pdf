## Trello To PDF

Renders trello boards as easily-printable webpages.

Forked from the [brilliant gist](https://gist.github.com/mathiasrw/8710615) by @mathiasrw. Hosted on netlify.

### Usage

Export a board using the right panel [as per these instructions](https://help.trello.com/article/747-exporting-data-from-trello-1).
Then, drag the downloaded file into the UI away you go. You can choose to exclude
lists using the check boxes at the top. They are not included in the final output.

For public boards you can paste the URL into the box and it will load the json automatically.

Alternatively, you can click <a href="javascript:(function(){var loc=location.href;loc=loc.replace('trello.com','trello.arlyon.dev'); window.location.assign(loc)})()">this bookmarklet</a> (drag it to your bookmarks bar!) on any public trello page to instantly get the document for it.

### Development

PRs are welcome. This project is formatted with the default
settings from prettier.

```bash
prettier --write .
```

Running the app requires that you have an SPA-compatible
server serving the files otherwise loading boards
directly won't work. Luckily there is a handy docker container that you can use.

```bash
# optionally build
docker build . -t arlyon/nginx-spa
docker run -it -p 8080:80 -v $(pwd):/app arlyon/nginx-spa
```

Then you can open it up at `localhost:8080`.
