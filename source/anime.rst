Anime
==================================

**Title languages**
	To make supporting the user *title_language* option easier, if the english or japanese titles are not available their values will be replaced the the standard romaji title.

**Anime Model**
::
	{
		"id": 1,
		"title_romaji": "Cowboy Bebop",
		"type": "TV",
		"image_url_med": "http://anilist.co/img/dir/anime/med/1.jpg",
		"image_url_sml": "http://anilist.co/img/dir/anime/sml/1.jpg",
		"start_date": "1998-04-03T21:00:00+09:00",
		"end_date": "1999-04-24T21:00:00+09:00",
		"classification": "R - 17+ (violence & profanity)",
		"hashtag": null,
		"source": null,
		"title_japanese": "カウボーイビバップ",
		"title_english": "Cowboy Bebop",
		"synonyms": [],
		"description": "Enter a world in the distant future, where Bounty Hunters roam the solar system. Spike and Jet, bounty hunting partners, set out on journeys in an ever struggling effort to win bounty rewards to survive.<br><br>\nWhile traveling, they meet up with other very interesting people. Could Faye, the beautiful and ridiculously poor gambler, Edward, the computer genius, and Ein, the engineered dog be a good addition to the group?",
		"genres": [
			"Action",
			"Adventure",
			"Comedy",
			"Drama",
			"Sci-Fi",
			"Space"
		],
		"image_url_lge": "http://anilist.co/img/dir/anime/reg/1.jpg",
		"image_url_banner": "http://anilist.co/img/dir/anime/banner/1.jpg",
		"duration": 24,
		"airing_status": "finished airing",
		"average_score": "86.8",
		"total_episodes": 26,
		"youtube_id": null,
		"adult": false,
		"popularity": 7574,
		"relation_type": null,
		"role": null,
		"list_stats": {
			"plan_to_watch": 1673,
			"watching": 421,
			"completed": 4855,
			"on_hold": 511,
			"dropped": 114
		},
		"airing": {
			"time": "2015-04-12T00:00:00+09:00",
			"countdown": 497524,
			"next_episode": 2
		}
	}

**Small Anime Model**
::
	{
		"id": 1,
		"title_romaji": "Cowboy Bebop",
		"type": "TV",
		"image_url_med": "http://anilist.co/img/dir/anime/med/1.jpg",
		"image_url_sml": "http://anilist.co/img/dir/anime/sml/1.jpg",
		"title_japanese": "カウボーイビバップ",
		"title_english": "Cowboy Bebop",
		"synonyms": [],
		"image_url_lge": "http://anilist.co/img/dir/anime/reg/1.jpg",
		"airing_status": "finished airing",
		"average_score": "86.8",
		"total_episodes": 26,
		"adult": false,
		"popularity": 7574,
		"relation_type": null,
		"role": null
	}

==================================
Basic
==================================

Url
::
  GET: anime/{id}

Returns anime model.

==================================
Page
==================================

Url
::
  GET: anime/{id}/page

Returns anime model with the following:
::
	Up to 9 small model characters (ordered by main role) with Japanese small model actors
	Up to 9 small model staff
	Up to 2 small model reviews with their users
	Relations (small model anime)
	Manga relations (small model manga)
	Studios
	External links

==================================
Characters / Staff
==================================

Url
::
  GET: anime/{id}/characters
  alt: anime/{id}/staff
  alt: anime/{id}/actors

Returns anime model with the following:
::
	Small model characters (ordered by main role) with small model actors
	Small model staff

==================================
Airing
==================================
Url
::
  GET: anime/{id}/airing

* Key: Episode number
* Value: Airing Time

==================================
Browse
==================================
Returns up to 40 small anime models if paginating.

Browse
::
	Get: browse/anime

	Url Parms:
	year           : 4 digit year e.g. "2014"
	season         : "winter" || "spring" || "summer" || "fall"
	type           : "Tv"  || "Movie"  || "Special"  || "OVA"  || "ONA"  || "Tv Short"
	status         : "Not Yet Aired" || "Currently Airing" || "Finished Airing" || "Cancelled"
	genres         : Comma separated genre strings. e.g. "Action,Comedy" Returns anime that have ALL the genres.
	genres_exclude : Comma separated genre strings. e.g. "Drama" Excludes returning anime that have ANY of the genres.
	sort           : "id" || "score" || "popularity" || "start date" || "end date" Sorts results, default ascending order. Append "-desc" for descending order e.g. "id-desc"
	airing_data    : "airing_data=true" Includes anime airing data in small models
	full_page      : "full_page=true" Returns all available results. Ignores pages. Only available when status="Currently Airing" or season is included
	page           : int


Genre List
::
	GET: genre_list

List of genres for use with browse queries

*The old browse API endpoints will continue to be supported until the next major API version update*

==================================
Favourite [POST]
==================================

Toggle favourite
::
	POST: anime/favourite

Payload
::
	id: (int) anime id

==================================
Search
==================================

Url
::
  GET: anime/search/{query}

Returns small anime models.
