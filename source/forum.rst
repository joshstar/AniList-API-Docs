Forum
==================================


**Tag Ids**
::
    1.  Anime
    2.  Manga
    3.  Light Novels
    4.  Visual Novels
    5.  Release Discussion
    6.  (Unused)
    7.  General
    8.  News
    9.  Music
    10. Gaming
    11. Site Feedback
    12. Bug Reports
    13. Site Announcements
    14. List Customisation
    15. Recommendations
    16. Forum Games
    17. Misc
    18. AniList Apps

==================================
Feeds
==================================

All of the following feeds are returned in the same data format:
First they include pagination data
::
    "total": 56,
    "per_page": 22,
    "current_page": 1,
    "last_page": 3,
    "from": 1,
    "to": 22,

Next, the threads array is within "data":
::
    "data": [
        {
            "id": 61,
            "title": "Example Thread",
            "sticky": 1,
            "last_reply": "2014-10-20 09:31:57",
            "reply_count": 1,
            "view_count": 19,
            "tags": [
            {
                "id": 7,
                "name": "General"
            }
            ],
            "tags_anime": [
                {
                    "id": 18897,
                    "thread_id": 60,
                    "tag_id": 18897,
                    "anime": [
                        {
                            "id": 18897,
                            "title_romaji": "Nisekoi",
                            "type": "TV",
                            "image_url_med": "http://anilist.co/img/dir/anime/med/18897.jpg",
                            "image_url_sml": "http://anilist.co/img/dir/anime/sml/18897.jpg",
                            "title_japanese": "ニセコイ",
                            "title_english": "Nisekoi",
                            "image_url_lge": "http://anilist.co/img/dir/anime/reg/18897.jpg",
                            "airing_status": "currently airing",
                            "average_score": "79.3",
                            "total_episodes": 20,
                            "adult": false,
                            "relation_type": null,
                            "role": null
                        }
                    ]
                }
            ],
            "tags_manga": [],
            "user": {
                "id": 1,
                "display_name": "Josh",
                "image_url_lge": "http://img.anilist.co/user/reg/1.png",
                "image_url_med": "http://img.anilist.co/user/sml/1.png"
            },
            "reply_user": {
                "id": 1,
                "display_name": "Josh",
                "image_url_lge": "http://img.anilist.co/user/reg/1.png",
                "image_url_med": "http://img.anilist.co/user/sml/1.png"
            }
    }, ...etc

* When there is no reply to a thread *last_reply* will be set to the creation date of the thread.
* *tags_anime* and *tags_manga* include an array of small anime/manga models
* *user* includes the small user model of the thread's creator.
* *reply_user* includes the small user model for the user who last commented in the thread.
* *sticky* is a boolean.

**Recent**
::
  GET: forum/recent

    Url Params:
        page : page number

Returns threads ordered by most recent activity or creation.

**New**
::
  GET: forum/new

    Url Params:
        page : page number

Returns threads ordered by most recent creation.

**Subscribed**
::
  GET: forum/subscribed

    Url Params:
        page : page number

Returns threads the user has subscribed to, ordered by most recent activity or creation.

*Note: Only available via authorization code/pin grant.*

**Tags**
::
   GET: forum/tag

   Url Params:
       tags  : Comma separated tag ids
       anime : Comma separated anime ids
       manga : Comma separated manga ids
       page : page number

Returns threads which belong to all of the included tags, ordered by most recent activity or creation.

==================================
Thread
==================================
Url
::
    GET: forum/thread/{id}

Thread data (No comments):
::
    {
        "id": 1,
        "user_id": 2,
        "title": "[Spoilers] Anime! (Episode 1 Discussion)",
        "body": "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed quis posuere urna.",
        "sticky": null,
        "locked": null,
        "last_reply": "2014-10-07 10:29:22",
        "last_reply_user": 1,
        "deleted_at": null,
        "created_at": "2014-10-07 10:23:21",
        "reply_count": 2,
        "view_count": 61,
        "subscribed": false,
        "page_data": {
            "total_root": 11,
            "per_page": 10,
            "current_page": 1,
            "last_page": 2,
            "from": 1,
            "to": 10
        },
        "tags": [
            {
                "id": 3,
                "name": "Light Novels"
            }
        ],
        "tags_anime": [
            {
                "id": 30,
                "thread_id": 1,
                "tag_id": 30,
                "anime": [
                    {
                        "id": 30,
                        "title_romaji": "Neon Genesis Evangelion",
                        "type": "TV",
                        "image_url_med": "http://anilist.co/img/dir/anime/med/30.jpg",
                        "image_url_sml": "http://anilist.co/img/dir/anime/sml/30.jpg",
                        "title_japanese": "新世紀エヴァンゲリオン",
                        "title_english": "Neon Genesis Evangelion",
                        "image_url_lge": "http://anilist.co/img/dir/anime/reg/30.jpg",
                        "airing_status": "finished airing",
                        "average_score": "82",
                        "total_episodes": 26,
                        "adult": false,
                        "relation_type": null,
                        "role": null
                    }
                ]
            }
        ],
        "tags_manga": [],
        "user": {
            "id": 1,
            "display_name": "Josh",
            "image_url_lge": "http://img.anilist.co/user/reg/1.png",
            "image_url_med": "http://img.anilist.co/user/sml/1.png"
        },
        "reply_user": {
            "id": 1,
            "display_name": "Josh",
            "image_url_lge": "http://img.anilist.co/user/reg/1.png",
            "image_url_med": "http://img.anilist.co/user/sml/1.png"
        }
    }


* *page_data* includes pagination for only the root level comments
* *tags_anime* and *tags_manga* include an array of small anime/manga models
* *user* includes the small user model of the thread's creator.
* *reply_user* includes the small user model for the user who last commented in the thread.
* *sticky*, *locked* and *subscribed* are booleans.

**Thread Comments**

Included within "comments":
::
    "comments": [
        {
            "id": 139,
            "parent_id": null,
            "user_id": 1,
            "thread_id": 61,
            "comment": "root comment 1",
            "created_at": "2014-10-20 09:31:57",
            "updated_at": "2014-10-26 23:52:58",
            "user": {
                "id": 1,
                "display_name": "Josh",
                "image_url_lge": "http://img.anilist.co/user/reg/1.png",
                "image_url_med": "http://img.anilist.co/user/sml/1.png"
            },
            "children": [
                {
                    "id": 142,
                    "parent_id": 139,
                    "user_id": 1,
                    "thread_id": 61,
                    "comment": "child comment 1",
                    "created_at": "2014-10-26 23:52:39",
                    "updated_at": "2014-10-26 23:53:06",
                    "user": {
                        "id": 1,
                        "display_name": "Josh",
                        "image_url_lge": "http://img.anilist.co/user/reg/1.png",
                        "image_url_med": "http://img.anilist.co/user/sml/1.png"
                    },
                    "children": []
                }
            ]
        },
        {
            "id": 143,
            "parent_id": null,
            "user_id": 1,
            "thread_id": 61,
            "comment": "root comment 2",
            "created_at": "2014-10-26 23:52:53",
            "updated_at": "2014-10-26 23:53:16",
            "user": {
                "id": 1,
                "display_name": "Josh",
                "image_url_lge": "http://img.anilist.co/user/reg/1.png",
                "image_url_med": "http://img.anilist.co/user/sml/1.png"
            },
            "children": []
        }
    ]

* Comments have children comments themselves, that can have children comments, and so on and so forth.

==================================
Create thread [POST]
==================================

Create thread
::
    POST: forum/thread

Payload
::
    title       : (string) thread title
    body        : (string) thread body
    tags        : Comma separated tag ids
    tags_anime  : Comma separated anime ids
    tags_manga  : Comma separated manga ids

==================================
Edit thread [PUT]
==================================

Edit thread
::
    PUT: forum/thread

Payload
::
    id          : (int) thread id
    title       : (string) thread title
    body        : (string) thread body
    tags        : Comma separated tag ids
    tags_anime  : Comma separated anime ids
    tags_manga  : Comma separated manga ids

==================================
Remove thread [DELETE]
==================================

Remove thread
::
    DELETE: forum/thread/{thread_id}

==================================
Thread subscribe [POST]
==================================

Toggle thread subscribe
::
    POST: forum/comment/subscribe

Payload
::
    thread_id: (int) thread id

==================================
Create comment [POST]
==================================

Edit thread
::
    POST: forum/comment

Payload
::
    thread_id  : (int) thread id
    comment    : (string) comment text
    reply_id   : (int) comment id (only when replying)

==================================
Edit comment [PUT]
==================================

Edit thread
::
    PUT: forum/comment

Payload
::
    id      : (int) comment id
    comment : (string) comment text

==================================
Remove comment [DELETE]
==================================

Remove thread
::
    DELETE: forum/comment/{comment_id}

==================================
Search
==================================
Url
::
  GET: forum/search/{query}

Returns search feed threads.
