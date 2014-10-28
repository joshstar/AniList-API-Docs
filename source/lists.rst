User Lists
==================================

**List score type**
::
	0. 10 Point (0-10 int)
	1. 100 Point (0-100 int)
	2. 5 Star (1-5 " Star" String)
	3. 3 Smiles (":(",":|",":)" String)
	4. 10 Point decimal (0.0 - 10.0 Float)

* The AniList API will automatically convert and output the correct score format for the user's type.
* String score types with the score value 0 will output "-".

**List score order**
::
	0. Score
	1. Alphabetical

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

==================================
Create entry [POST]
==================================

==================================
Edit entry [PUT]
==================================

==================================
Remove entry [DELETE]
==================================
