User
==================================

==================================
Basic
==================================
Url
::
  GET: user/{id || displayname}

Returns a user model.
==================================
Page
==================================
Url
::
  GET: user/{id || displayname}/page

Returns a user model with favourites.

==================================
Activity
==================================
**User Activity**:
::
  GET: user/{id || displayname}/activity

  Url Params:
      page : page number

**Current user's activity feed**:
::
  GET: user/activity

  Url Params:
      page : page number

Returns the activity of the current user and the users they are following.

==================================
Create activity [POST]
==================================

==================================
Remove activity [DELETE]
==================================

==================================
Create activity reply [POST]
==================================

==================================
Remove activity reply [DELETE]
==================================

==================================
Notifications
==================================

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

==================================
Airing
==================================

==================================
Reviews
==================================

==================================
Search
==================================
