Studio
==================================

**Studio Model**
::
	{
		"studio_name": "Studio Pierrot",
		"studio_wiki": "http://en.wikipedia.org/wiki/Pierrot_(company)",
		"id": 1,
		"main_studio": null
	}

==================================
Basic
==================================
Url
::
  GET: studio/{id}

Returns a studio model.

==================================
Page
==================================
Url
::
  GET: studio/{id}/page

Returns a studio model with small anime models.

==================================
Search
==================================

Url
::
  GET: studio/search/{query}

Returns studio models.