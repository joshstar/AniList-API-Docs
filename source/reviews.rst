Reviews
==================================


Reivew Model
::
    {
        "id": 435,
        "date": "2014-05-03 14:44:15",
        "rating": 2,
        "rating_amount": 2,
        "summary": "Review Summary",
        "private": 0,
        "user_rating": 1,
        "text": "Review text, it was good.",
        "score": 94,
        "anime": (anime small model),
        "user": (user small model)
    }

* rating: Positive user ratings of review.
* ratings_amount: All user ratings of review.
* user_rating: Current user rating of review. (0 no rating, 1 up/positive rating, 2 down/negative rating)

==================================
Review [GET]
==================================

Urls
::
    Anime GET: anime/review/{review_id}
    Manga GET: manga/review/{review_id}

Returns review model with small anime/manga and small user model.

==================================
Anime/Manga Reviews [GET]
==================================

Urls
::
    Anime GET: anime/{anime_id}/reviews
    Manga GET: manga/{manga_id}/reviews

Returns array of review models with anime/manga and small user model.

==================================
User Reviews [GET]
==================================

Url
::
    GET: user/{id || displayname}/reviews

Returns array of review models with anime/manga and small user model.


=============================================
Rate Review [POST]
=============================================
Urls
::
    Anime POST: anime/review/rate
    Manga POST: manga/review/rate

Payload
::
    id     : (int) id of review to rate
    rating : (int) 0 no rating, 1 up/positive rating, 2 down/negative rating

=============================================
Review - Create [POST] / Edit [PUT]
=============================================
Create
::
    Anime POST: anime/review
    Manga POST: manga/review

Edit
::
    Anime PUT: anime/review
    Manga PUT: manga/review

Payload
::
    anime_id : (int) anime_id of review anime. (Change to manga_id for manga)
    text     : (string) Review text (min 2000 characters)
    summary  : (string) Review summary (min 20, max 120 characters)
    private  : (int) 0 or 1 boolean
    score    : (int) 0-100 review score

==================================
Remove Review [DELETE]
==================================

Urls
::
	Anime DELETE: anime/review
	Manga DELETE: manga/review

Payload
::
    id: id of review to remove
