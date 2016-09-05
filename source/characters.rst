Characters
==================================

**Character model**
::
	{
		"name_alt": "",
		"info": "Height: 6&#039; 1&quot;  Weight: 155    Spike Spiegel is a tall and lean 27-year-old bounty hunter born on Mars. The inspiration for Spike is found in martial artist Bruce Lee who uses the martial arts style of Jeet Kune Do as depicted in Session 8, &quot;Waltz For Venus&quot;. He has fluffy, dark green hair (which is inspired by Yusaku Matsuda&#039;s) and reddish brown eyes, one of which is artificial and lighter than the other. He is usually dressed in a blue leisure suit, with a yellow shirt and Lupin III inspired boots. A flashback in Session 6 revealed it was his fully functioning right eye which was surgically replaced by the cybernetic one (although Spike himself may not have conscious recollection of the procedure since he claims to have lost his natural eye in an &quot;accident&quot;). One theory is that his natural eye may have been lost during the pre-series massacre in which he supposedly &quot;died&quot;. The purpose of this cybernetic eye is never explicitly stated, though it apparently gives him exceptional hand-eye coordination - particularly with firearms (Spike&#039;s gun of choice is a Jericho 941, as seen throughout the series). In the first episode, when facing a bounty-head using Red Eye, Spike mocks him, calling his moves &quot;too slow&quot;. At first, this seems like posturing on Spike&#039;s part, but even with his senses and reflexes accelerated to superhuman levels by the drug, the bounty cannot even touch Spike. A recurring device throughout the entire show is a closeup on Spike&#039;s fully-natural left eye before dissolving to a flashback of his life as part of the syndicate. As said by Spike himself in the last episode, his right eye &quot;only sees the present&quot; and his left eye &quot;only sees the past.&quot; Spike often has a bent cigarette between his lips, sometimes despite rain or &quot;No Smoking&quot; signs.",
		"id": 1,
		"name_first": "Spike",
		"name_last": "Spiegel",
		"name_japanese": "スパイク・スピーゲル",
		"image_url_lge": "http://anilist.co/img/dir/character/reg/1.jpg",
		"image_url_med": "http://anilist.co/img/dir/character/med/1.jpg",
		"role": null
	}


**Small Character Model**
::
	{
		"id": 1,
		"name_first": "Spike",
		"name_last": "Spiegel",
		"image_url_lge": "http://anilist.co/img/dir/character/reg/1.jpg",
		"image_url_med": "http://anilist.co/img/dir/character/med/1.jpg",
		"role": "Main",
	}

==================================
Basic
==================================
Url:
::
	GET: character/{id}

Returns character model.

==================================
Page
==================================
Url:
::
	GET: character/{id}/page

Returns characters model with the following:
::
	Small model anime with small model character
	Small model anime staff
	Small model manga staff

==================================
Favourite [POST]
==================================

Toggle favourite
::
	POST: character/favourite

Payload
::
	id: (int) character id

==================================
Search
==================================
Url
::
  GET: character/search/{query}

Returns small character models.
