# pirateflix SDK
![https://pirateflix.app [![npm downloads](https://pirateflix.app [![](https://pirateflix.app [![](https://pirateflix.app time to resolve an issue](https://pirateflix.app "Average time to resolve an issue") [![Percentage of issues still open](https://pirateflix.app "Percentage of issues still open")[![Gitter chat](https://pirateflix.app SDK for pirateflix applications making it easier to retrieve movies / shows with meta data

### Installation
```shell
$ npm install --save pirateflix-sdk
```

## Examples
```js
import SDK from 'pirateflix-sdk'

const movies = await SDK.getMovies()
const movie = await SDK.getMovie({ ids: { imdb: '' } })

const shows = await SDK.getShows()
const show = await SDK.getShow({ ids: { imdb: '', tmdb: '' }}) // One of the two, imdb is preferred

// Or for slower internet connections you can partial load a show
const showBasic = await SDK.getBasicShow(imdbId)

// getShowMeta retrieves data from The Movie DB for better episode info and season / episode images
// Basically runs getShowIds and getShowSeasonsMeta
const showWithMeta = await SDK.getShowMeta(showBasic) 

// To only retrieve the ids for a show
const showWithIds = await SDK.getShowIds({ids: { imdb: '', tmdb: '' }})

// To only retrieve the seasons meta
const showWithSeasons = await SDK.getShowSeasonsMeta(showBasic)

// To retrieve recommendations for a certain show
const recommendations = await SDK.getShowRecommendations({ ids: { tmdb: '' } })
```

### Adapters
You can add adapters handy for if you want to add attributes to movies / shows 
```js
import SDK from 'pirateflix-sdk'
import DefaultAdapter from 'pirateflix-sdk/Adapter'

class MyAdapter extends DefaultAdapter {

  /**
   * Get's called after the movies are fetched and before they are returned
   * 
   * @param movies
   * @returns {*}
   */
  checkMovies = movies => movies

  /**
   * Get's called after the movie is fetched and before they it is returned
   *
   * @param movie
   * @returns {*}
   */
  checkMovie = movie => movie

  /**
   * Get's called after the shows are fetched and before they are returned
   *
   * @param shows
   * @returns {*}
   */
  checkShows = shows => shows

  /**
   * Get's called after the show is fetched and before they it is returned
   *
   * @param show
   * @returns {*}
   */
  checkShow = show => show
}

SDK.addAdapter(new MyAdapter())

```

### Movie output
```JSON
// TODO
```

### Show output
```JSON
// TODO
```

## [License](https://pirateflix.app project is [MIT licensed](./LICENSE).

## Collaboration

If you have questions or [issues](https://pirateflix.app please [open an issue](https://pirateflix.app