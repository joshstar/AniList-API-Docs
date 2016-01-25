Introduction
==================================
**All** AniList Api url's featured in this documentation require the following url prefix:
::
    https://anilist.co/api/

**HTTPS is required**
    If a client requests a HTTP url they will **not** be redirected to the HTTPS variant.

**API Terms of use**
    - Free for non-commercial use.
    - Using the AniList API as a backup or data storage service is strictly prohibited.
    - \'Hoarding\' or mass collection of data from the AniList API is strictly prohibited.

    If you would like to use the AniList API in a commercial client (this includes ads and in-app purchases)
    just drop me an email joshstar [a-t] mail [do-t] com and I'll get back to you eventually.
    With the current usage of the API it's rather unlikely any kind of profit cut etc will be necessary.

**Naming Guidelines**
    Applications or services that utilizes the AniList API must adhere to our naming guidelines (case insensitive):
    
    - If "AniList" or "AniChart" are used in the title/name of the application you must clearly state they are an unofficial app by appending either "UNOFFICIAL" or "for AniList"/"for AniChart" to the title/name of the application.
    - Just the title/name "AniList" and "AniChart" are strictly NOT permitted.


**Adult content and application stores**
    We feel we should mention many app-stores like the Apple app store prohibit 18+ content.
    If you're thinking about providing your client via a third-party service you should check their official state on the matter.
    Where we can, we provide an adult boolean in anime/manga API data, however we can not 100% ensure that this will always be accurate
    or that our definition of 'adult' content meets the same standards of other services.
    Specifically 'Ecchi' shows are not included in the 'adult' boolean, which is known to have caused issues with Google Adsense and the Apple app-store in the past.

    We can also not ensure the data provided by our user's always be non-adult, (primarily activity and forum data) however we do try to remove this data as soon as possible.

    We recommend you do additional checks and limit the data shown on your client if necessary, to comply with the standards of any service you may be using.


==================================
Creating a client
==================================

Log into your AniList account (or create one if you haven't already) and go to `the developer settings <https://anilist.co/settings/developer>`_. Click 'Create New Client' and enter your client's information, once saved you will receive your client id and secret.


==================================
Terminology
==================================

- **Access token** - A token used to access protected resources
- **Authorization code** - An intermidiary token generated when a user authorizes a client to access protected resources on their behalf. The client receives this token and exchanges it for an access token.
- **Client** - An application which accesses protected resources on behalf of the resource owner. The client could be hosted on a server, desktop, mobile app or other device.
- **Grant** - A grant is a method of acquiring an access token.
- **Resource owner** - The owner of a protected resource, usually the user.
- **Resource server** - The AniList API server, which sits in front of protected resources and is capable of accepting and responsing to protected resource requests using access tokens.

`Terminology courtesy of Alex Bilbie <http://oauth2.thephpleague.com/terminology/>`_
