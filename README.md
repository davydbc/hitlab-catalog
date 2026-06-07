# Hitster Catalogs

This repository contains song catalogs used by a custom game inspired by Hitster.

Each catalog is represented by a JSON file containing a collection of cards, where each card corresponds to a song.

## Card Structure

Each card must contain the following fields:

| Field         | Required | Description                                                                    |
|---------------|----------|--------------------------------------------------------------------------------|
| `song_title`  | Yes      | Song title.                                                                    |
| `song_author` | Yes      | Artist or band who performs the song.                                          |
| `song_year`   | Yes      | Year the song was originally released.                                         |
| `spotify_url` | Yes      | Spotify track URL used to play the song during the game.                       |
| `film`        | No       | Movie, TV series, video game, musical, or other work associated with the song. |
| `film_year`   | No       | Release year of the associated work.                                           |

### Example

```json
{
  "film": "The Lion King",
  "film_year": 1994,
  "song_title": "Circle of Life",
  "song_author": "Elton John",
  "song_year": 1994,
  "spotify_url": "https://open.spotify.com/track/xxxxxxxxxxxxxxxxxxxxxx"
}
```

## Catalog Organization

Each catalog is stored as a JSON file in the repository root following this naming convention:

```text
{category}_catalog.json
```

Examples:

```text
bso_catalog.json
rock_catalog.json
anime_catalog.json
eurovision_catalog.json
```

Where `category` identifies the theme or type of songs included in the catalog.

## Catalog Format

A catalog is a JSON array containing one or more song cards:

```json
[
  {
    "film": "The Lion King",
    "film_year": 1994,
    "song_title": "Circle of Life",
    "song_author": "Elton John",
    "song_year": 1994,
    "spotify_url": "https://open.spotify.com/track/xxxxxxxxxxxxxxxxxxxxxx"
  },
  {
    "song_title": "Bohemian Rhapsody",
    "song_author": "Queen",
    "song_year": 1975,
    "spotify_url": "https://open.spotify.com/track/yyyyyyyyyyyyyyyyyyyyyy"
  }
]
```

## Guidelines

* Years must be represented as four-digit integers.
* `spotify_url` must point directly to a Spotify track (`https://open.spotify.com/track/...`).
* Song titles, artist names, and work titles should use their official names whenever possible.
* Optional fields (`film` and `film_year`) should only be included when applicable.
* Each card must represent a single song.
* Duplicate songs within the same catalog should be avoided.
* The `song_year` should correspond to the song's original release year, not a remaster or re-release date unless
  explicitly intended.
