Staff
==================================

**Staff/Actor Model**
::
	{
		"dob": 9081972,
		"website": "http://www.atomicmonkey.jp/jp/amprofile/seki.html",
		"info": "Hometown: Tokyo, Japan Blood type: AB  Alias: Monto Hiraku  Also Known as: Seki Mondoya (門戸 開)",
		"id": 1,
		"name_first": "Tomokazu",
		"name_last": "Seki",
		"name_first_japanese": "智一",
		"name_last_japanese": "関",
		"image_url_lge": "http://anilist.co/img/dir/person/reg/1.jpg",
		"image_url_med": "http://anilist.co/img/dir/person/med/1.jpg",
		"language": "Japanese",
		"role": null
	}


**Small Staff/Character Model**
::
	{
		"id": 14,
		"name_first": "Megumi",
		"name_last": "Hayashibara",
		"image_url_lge": "http://anilist.co/img/dir/person/reg/14.jpg",
		"image_url_med": "http://anilist.co/img/dir/person/med/14.jpg",
		"language": "Japanese",
		"role": null
	}

==================================
Basic
==================================
Url:
::
	GET: staff/{id}
	alt: actor/{id}

Returns staff model.

==================================
Page
==================================
Url:
::
	GET: staff/{id}/page
	alt: actor/{id}

Returns staff model with the following:
::
	Small model anime with small model actors
	Small model manga

==================================
Favourite [POST]
==================================

==================================
Search
==================================

Url
::
  GET: staff/search/{query}
  alt: actor/search/{query}

Returns small staff models.