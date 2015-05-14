User Lists
==================================

==================================
Animelist
==================================
Url
::
	GET: user/{id || displayname}/animelist

Raw
::
	GET: user/{id || displayname}/animelist/raw

Raw outputs the same as the standard animelist output but the without anime relation data.

=============================================
Anime list - Create entry [POST] / Edit entry [PUT]
=============================================
Create
::
	POST: animelist

Edit
::
	PUT: animelist

Payload
::
	id: (int) anime_id of list item
	list_status: (String) "watching" || "completed" || "on-hold" || "dropped" || "plan to watch"
	score: (See bottom of page - List score types)
	score_raw: (int) 0-100 (See bottom of page - Raw score)
	episodes_watched: (int)
	rewatched: (int)
	notes: (String)
	advanced_rating_scores: comma separated scores, same order as advanced_rating_names
	custom_lists: comma separated 1 or 0, same order as custom_list_anime
	hidden_default: (int) 0 || 1


==================================
Mangalist
==================================
Url
::
	GET: user/{id || displayname}/mangalist

Raw
::
	GET: user/{id || displayname}/mangalist/raw

Raw outputs the same as the standard mangalist output but without the manga relation data.

=============================================
Manga list - Create entry [POST] / Edit entry [PUT]
=============================================
Create
::
	POST: mangalist

Edit
::
	PUT: mangalist

Payload
::
	id: (int) manga_id of list item
	list_status: (String) "reading" || "completed" || "on-hold" || "dropped" || "plan to read"
	score: (See bottom of page - List score types)
	score_raw: (int) 0-100 (See bottom of page - Raw score)
	volumes_read: (int)
	chapters_read: (int)
	reread: (int)
	notes: (String)
	advanced_rating_scores: comma separated scores, same order as advanced_rating_names
	custom_lists: comma separated 1 or 0, same order as custom_list_manga
	hidden_default: (int) 0 || 1


==================================
Remove entry [DELETE]
==================================

Anime list
::
	DELETE: animelist/{anime_id}

Manga list
::
	DELETE: mangalist/{manga_id}

==================================
List Scores
==================================

**List score type**
::
	0. 10 Point (0-10 int)
	1. 100 Point (0-100 int)
	2. 5 Star (0-5 int)
	3. 3 Smiles (":(",":|",":)" String)
	4. 10 Point decimal (0.0 - 10.0 Float)

* The AniList API will automatically convert and output the correct score format for the user's type.
* String score types with the score value 0 will output "-".

**Score Raw**

If you are using a type-safe language the multiple return types of the usual list score can be a pain to work with, so you'll want to use score_raw instead.

Score raw will return the unformatted 0-100 int of the users score, this will need to be formatting on your client into the correct score type for the current user.

Score Raw breakpoints:

5 Star
::
	1 : 1-29
	2 : 30-49
	3 : 50-69
	4 : 70-89
	5 : 90-100

Smiley
::
	:( : 1-30
	:| : 31-60
	:) : 61-100

* When converting to a lower score format, ensure to always floor (round down) the scores down to the nearest breakpoint. Do not just round them.

**List score order**
::
	0. Score
	1. Alphabetical
