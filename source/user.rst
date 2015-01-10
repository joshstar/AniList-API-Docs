User
==================================

**User Model**
::
	{
		"id": 1,
		"display_name": "Josh",
		"anime_time": 54067,
		"manga_chap": 587,
		"about": "Admin of this site and AniChart.net. Basically a Comp Sci student with interest in anime, web dev, gaming, and technology :)\r\nYou can follow me on twitter  [@J0shstar](https://twitter.com/J0shStar)",
		"list_order": 0,
		"adult_content": true,
		"following": false,
		"image_url_lge": "http://img.anilist.co/user/reg/1.png",
		"image_url_med": "http://img.anilist.co/user/sml/1.png",
		"image_url_banner": "http://i.imgur.com/ZHAUS4K.jpg",
		"title_language": "romaji",
		"score_type": 4,
		"custom_list_anime": [
			"",
			"Fall Anime",
			"Summer Anime",
			"",
			""
		],
		"custom_list_manga": [
			"",
			"",
			"",
			"",
			""
		],
		"advanced_rating": 1,
		"advanced_rating_names": [
			"Story",
			" Characters",
			" Visuals",
			" Audio",
			" Enjoyment"
		],
		"notifications": 0
	}

**Small User Model**
::
	{
		"id": 1,
		"display_name": "Josh",
		"image_url_lge": "http://img.anilist.co/user/reg/1.png",
		"image_url_med": "http://img.anilist.co/user/sml/1.png"
	}

==================================
Basic
==================================
Url
::
  GET: user/{id || displayname}

Returns a user model.

Current authenticated user
::
	GET: user

Returns user model. Only available for *authorization code* or *authorization pin* grant types.

==================================
Activity
==================================
**User Activity**:
::
  GET: user/{id || displayname}/activity

  Url Params:
      page : page number

Returns the activity of the user and activity messages from of other users.

**Current user's activity feed**:
::
  GET: user/activity

  Url Params:
      page : page number

Returns the activity of the current user and the users they are following.

==================================
Create activity [POST]
==================================

**Activity status**
::
	POST: user/activity

Payload
::
	text: (string) activity text


**Activity message**
::
	POST: user/activity

Payload
::
	text: (string) activity text
	messenger_id: (int) recipient user id


**Activity reply**
::
	POST: user/activity

Payload
::
	text: (string) activity text
	reply_id: (int) activity id


==================================
Remove activity [DELETE]
==================================

**Remove activity**
::
	DELETE: user/activity

Payload
::
	id: (int) activity id

**Remove activity reply**
::
	DELETE: user/activity/reply

Payload
::
	id: (int) activity reply id

==================================
Notifications
==================================
Url
::
  GET: user/notifications

Returns up to 10 notifications of the current user.


**Count**
::
  GET: user/notifications/count

Returns int of current outstanding notifications of current user.

*Note: Only available via authorization code grant.*

==================================
Followers & Following
==================================
**Following**:
::
  GET: user/{id || displayname}/following

**Followers**:
::
  GET: user/{id || displayname}/followers


==================================
Follow/Unfollow [POST]
==================================

**Toggle follow**
::
	POST: user/follow

Payload
::
	id: (int) user id

==================================
Favourites
==================================
Url
::
  GET: user/{id || displayname}/favourites

Returns a user's favourites.

==================================
Airing
==================================
Url:
::
  GET: user/airing

  Url Params:
      limit : int number of entries returned

Returns anime list entry with small model anime, where the anime is currently airing and being currently watched by the user.

*Note: Only available via authorization code/pin grant.*

==================================
Search
==================================
Url
::
  GET: user/search/{query}

Returns small user models.
