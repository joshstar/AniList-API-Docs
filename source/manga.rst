Manga
==================================

**Title languages**
	To make supporting the user *title_language* option easier, if the english or japanese titles are not available their values will be replaced the the standard romaji title.

**Manga Model**
::
	{
		"id": 1,
		"title_romaji": "Monster",
		"type": "Manga",
		"start_date": "1994-12-05T00:00:00+09:00",
		"end_date": "2001-12-20T00:00:00+09:00",
		"title_japanese": "モンスター",
		"title_english": "Monster",
		"synonyms": [],
		"description": "Dr. Kenzo Tenma is a renowned young brain surgeon of Japanese descent working in Europe. Highly lauded by his peers as one of the great young minds that will revolutionize the field, he is blessed with a beautiful fianc&eacute; and is on the cusp of a high promotion in the hospital he works at. However, all of that is about to change with one critical decision that Dr. Tenma faces one night &ndash; whether to save the life of a young child or that of the town's mayor. Despite being pressured by his superiors to perform surgery on the mayor, his morals force him to perform the surgery on the young child, saving his life and forfeiting the mayor&rsquo;s. All of a sudden, Dr. Tenma&rsquo;s world is turned upside down by his decision leading to the loss of everything he previously had. A doctor is taught to believe that all life is equal; however, when a series of murders occur in the vicinity of Dr. Tenma, all of the evidence pointing to the young child who he saved, Tenma&rsquo;s beliefs are shaken.<br>\nNaoki Urasawa&rsquo;s Monster is a tale full of mystery, suspense and intrigue as Dr. Tenma journeys to find out the true identity of the young child. In turn, the fate of the world may depend on it.<br>\n[Written by MAL Rewrite]",
		"genres": [
			"Mystery",
			"Drama",
			"Psychological",
			"Seinen"
		],
		"image_url_lge": "http://anilist.co/img/dir/manga/reg/1.jpg",
		"image_url_med": "http://anilist.co/img/dir/manga/med/1.jpg",
		"image_url_banner": null,
		"publishing_status": "finished",
		"average_score": "90.2",
		"total_chapters": 162,
		"total_volumes": 18,
		"adult": false,
		"relation_type": null,
		"role": null
	}

**Small Manga Model**
::
	{
		"id": 698,
		"title_romaji": "Neon Genesis Evangelion",
		"type": "Manga",
		"title_japanese": "新世紀エヴァンゲリオン",
		"title_english": "Neon Genesis Evangelion",
		"synonyms": [],
		"image_url_lge": "http://anilist.co/img/dir/manga/reg/698.jpg",
		"image_url_med": "http://anilist.co/img/dir/manga/med/698.jpg",
		"publishing_status": "finished",
		"average_score": "85.3",
		"total_chapters": 95,
		"total_volumes": 14,
		"adult": false,
		"relation_type": null,
		"role": null
	}

==================================
Basic
==================================

Url
::
  GET: manga/{id}

Returns manga model.

==================================
Page
==================================

Url
::
  GET: manga/{id}/page

Returns manga model with the following:
::
	Up to 9 small model characters (ordered by main role)
	Up to 9 small model staff
	Up to 2 small model reviews with their users
	Relations (small model manga)
	Anime relations (small model anime)

==================================
Characters / Staff
==================================

Url
::
  GET: manga/{id}/characters
  alt: manga/{id}/staff

Returns anime model with the following:
::
	Small model characters (ordered by main role)
	Small model staff

==================================
Browse
==================================
Returns up to 30 small manga models.

Pagination
::
	URL Param: ?page=1

Recently added manga
::
	GET: manga/browse/recent

Currently publishing manga
::
	GET: manga/browse/publishing

Not yet published manga
::
	GET: manga/browse/upcoming

Manga by year
::
	GET: manga/browse/year/{year}

Year
::
	4 digit year. e.g. 2014
Season
::
	"winter"
	"spring"
	"summer"
	"fall"
	"autumn"

Pagination
::
	URL Param: ?page=1


==================================
Favourite [POST]
==================================

Toggle favourite
::
	POST: manga/favourite

Payload
::
	id: (int) manga id

==================================
Search
==================================
Url
::
  GET: manga/search/{query}

Returns small manga models.
