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
		"relation_type": null,
		"role": null,
		"airing": null
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
		"image_url_lge": "http://anilist.co/img/dir/anime/reg/1.jpg",
		"airing_status": "finished airing",
		"average_score": "86.8",
		"total_episodes": 26,
		"adult": false,
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
Reviews
==================================

==================================
Favourite [POST]
==================================

==================================
Search
==================================

Url
::
  GET: anime/search/{query}

Returns small anime models.