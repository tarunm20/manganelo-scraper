# Manganelo Scraper

Manganelo Scraper is a simple webscraper that uses the manganelo.com website to access information regarding the manga, manhwa, or manhua of your choice.

The information provided includes the name, alternative names, authors, the status, genres, the updated date, number of views, ratings, the description, the url, and links to all the chapters. Each chapter inlcudes the name, number of views, upload date, and url for the specific chapter.

## Installation

```bash
npm install manganelo-scraper
```

## Important
### Manga Object Structure

```bash
{
  name = string of manga name
  alternative = string of alternative manga names
  authors = string of authors
  status = string of status
  genres = array of strings, each element is a genre
  updated = string of date updated
  views = int number of views
  rating = object with two values. {ratingFromFive: string, votes: int}
  description = string of description
  url = string of url to manganelo page
  chapters = array of chapter objects
}
```

### Structure Example
```js
Manga {
  name: 'Nano Machine',
  alternative: [ '나노마신' ],
  authors: [ 'Han Joong Wueol Ya ' ],
  status: 'Ongoing',
  genres: [ 'Action', 'Adventure', 'Fantasy', 'Martial arts', 'Webtoons' ],
  updated: 'Jul 23,2020 - 20:05 PM',
  views: 39406,
  rating: { ratingFromFive: '4.75/5', votes: 291 },
  description: 'English, After being held in disdain and having his life put in danger, an orphan from the Demonic Cult, Cheon Yeo-Woon, has an unexpected visit from his descendant from the future who inserts a nano machine into Cheon Yeo-Woon’s body, which drastically changes Cheon Yeo-Woon’s life after its activation. The story of Cheon Yeo-Woon’s journey of bypassing the Demonic Cult and rising to become the best martial artist has just begun. French, La vie remplit d’infortune et d’épreuve de Cheo Yeo-Woon, bâtard et dernier dans l’ordre de succession, prit un tournant après qu’un de ses “descendant” venant du futur ait injecté des Nano Machines dans son corps. ',
  url: 'https://manganelo.com/manga/iu923224',
  chapters: [
    {
      chapter: 'Chapter 6',
      views: 4417,
      upload_date: 'Jul 23,20',
      url: 'https://manganelo.com/chapter/iu923224/chapter_6'
    },
    {
      chapter: 'Chapter 5',
      views: 6462,
      upload_date: 'Jul 16,20',
      url: 'https://manganelo.com/chapter/iu923224/chapter_5'
    },
    {
      chapter: 'Chapter 4',
      views: 5885,
      upload_date: 'Jul 15,20',
      url: 'https://manganelo.com/chapter/iu923224/chapter_4'
    },
    {
      chapter: 'Chapter 3',
      views: 6841,
      upload_date: 'Jul 09,20',
      url: 'https://manganelo.com/chapter/iu923224/chapter_3'
    },
    {
      chapter: 'Chapter 2',
      views: 7528,
      upload_date: 'Jun 25,20',
      url: 'https://manganelo.com/chapter/iu923224/chapter_2'
    },
    {
      chapter: 'Chapter 1',
      views: 8273,
      upload_date: 'Jun 14,20',
      url: 'https://manganelo.com/chapter/iu923224/chapter_1'
    }
  ]
}
```

### Chapter Object Structure
```bash
{
  chapter = string of chapter name
  views = int number of views
  upload_date = string of date the chapter was uploaded
  url = string of url to the specific chapter
}
```

### Structure Example

```js
{
  chapter: 'Chapter 1',
  views: 8273,
  upload_date: 'Jun 14,20',
  url: 'https://manganelo.com/chapter/iu923224/chapter_1'
}
```

## Examples
You can get a Manga object given the exact url from manganelo.com.

```js
const Manga = require('manganelo-scraper').scraper

//Get Manga object given the complete url from manganelo
Manga.getMangaDataFromURL('https://manganelo.com/manga/wo923110')
  .then(manga => {
    console.log(manga);
  });
```

### Response
```js
Manga {
  name: 'Omniscient Reader’S Viewpoint',
  alternative: [ 'ORV', '全知读者', '전독시', '전지적 독자 시점' ],
  authors: [ 'Sing Shong ' ],
  status: 'Ongoing',
  genres: [ 'Action', 'Adventure', 'Fantasy', 'Webtoons' ],
  updated: 'Jul 23,2020 - 20:06 PM',
  views: 255237,
  rating: { ratingFromFive: '4.85/5', votes: 1134 },
  description: '‘This is a development that I know of.’ The moment he thought that, the world had been destroyed, and a new universe had unfolded. The new life of an ordinary reader begins within the world of the novel, a novel that he alone had finished. ',
  url: 'https://manganelo.com/manga/wo923110',
  chapters: [
    {
      chapter: 'Chapter 14',
      views: 11971,
      upload_date: 'Jul 23,20',
      url: 'https://manganelo.com/chapter/wo923110/chapter_14'
    },
    {
      chapter: 'Chapter 13',
      views: 17311,
      upload_date: 'Jul 15,20',
      url: 'https://manganelo.com/chapter/wo923110/chapter_13'
    },
    {
      chapter: 'Chapter 12',
      views: 18514,
      upload_date: 'Jul 08,20',
      url: 'https://manganelo.com/chapter/wo923110/chapter_12'
    },
    {
      chapter: 'Chapter 11',
      views: 19547,
      upload_date: 'Jul 01,20',
      url: 'https://manganelo.com/chapter/wo923110/chapter_11'
    },
    {
      chapter: 'Chapter 10',
      views: 19460,
      upload_date: 'Jun 24,20',
      url: 'https://manganelo.com/chapter/wo923110/chapter_10'
    },
    {
      chapter: 'Chapter 9',
      views: 16000,
      upload_date: 'Jun 17,20',
      url: 'https://manganelo.com/chapter/wo923110/chapter_9'
    },
    {
      chapter: 'Chapter 8',
      views: 16239,
      upload_date: 'Jun 10,20',
      url: 'https://manganelo.com/chapter/wo923110/chapter_8'
    },
    {
      chapter: 'Chapter 7',
      views: 16510,
      upload_date: 'Jun 05,20',
      url: 'https://manganelo.com/chapter/wo923110/chapter_7'
    },
    {
      chapter: 'Chapter 6',
      views: 15031,
      upload_date: 'Jun 05,20',
      url: 'https://manganelo.com/chapter/wo923110/chapter_6'
    },
    {
      chapter: 'Chapter 5',
      views: 13505,
      upload_date: 'Jun 05,20',
      url: 'https://manganelo.com/chapter/wo923110/chapter_5'
    },
    {
      chapter: 'Chapter 4',
      views: 13213,
      upload_date: 'Jun 05,20',
      url: 'https://manganelo.com/chapter/wo923110/chapter_4'
    },
    {
      chapter: 'Chapter 3',
      views: 13573,
      upload_date: 'Jun 05,20',
      url: 'https://manganelo.com/chapter/wo923110/chapter_3'
    },
    {
      chapter: 'Chapter 2',
      views: 14084,
      upload_date: 'Jun 05,20',
      url: 'https://manganelo.com/chapter/wo923110/chapter_2'
    },
    {
      chapter: 'Chapter 1',
      views: 18687,
      upload_date: 'Jun 05,20',
      url: 'https://manganelo.com/chapter/wo923110/chapter_1'
    },
    {
      chapter: 'Chapter 0',
      views: 15416,
      upload_date: 'Jun 01,20',
      url: 'https://manganelo.com/chapter/wo923110/chapter_0'
    }
  ]
}
```

You can also get an array of Manga objects given a name.

```js
//Get an array of Manga objects from the search results
Manga.getMangaDataFromSearch('hero')
  .then(mangas => {
    for(let manga of mangas) {
      console.log(manga);
    }
  });
```

## Other Information
This is the first npm package I've ever created so if there are any errors please raise an issue or notify me.