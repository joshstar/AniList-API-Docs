Authentication
==================================

==================================
Which Grant type to use?
==================================

If you want to save, edit or remove (POST, PUT, DELETE) any AniList user (resource owner) data then you'll need to use the *authorization code* grant type.

If you only require reading of AniList data, then use *client credentials* grant type.

Both the current grant types have a client secret key, you are required to keep this **private**.


==================================
Grant: Authorization Code
==================================

The authorization code grant type allows the client access to view, add, edit and remove a resource owner's data on their behalf.
To do this we require the permission from the resource owner themselves, this will provide us with an *authorization code*,
which we can later exchange for the required *access token*.

Request authorization code:
::
  GET: auth/authorize

  Url Parms:
  grant_type    : "authorization_code"
  client_id     :  Client id
  redirect_uri  :  Client redirect uri
  response_type : "code"

This will direct the resource owner to a web page where they may choose to accept or deny the client.
If the resource owner is not currently logged in, they will be redirected to the standard AniList login page, then redirect back to the client approval page once logged in.

If the resource owner accepts the client, they will be redirected to the client's redirected uri.
A *code* parameter will be included in the redirect uri, this is **not** the access token, but instead the *authorization code* which will be exchanged for the access token in the next step.

Request access token:
::
  POST: auth/access_token

  Url Parms:
  grant_type    : "authorization_code"
  client_id     :  Client id
  client_secret :  Client secret
  redirect_uri  :  Client redirect uri
  code          :  Authorization code

Return example:
::
  {
    access_token: "ACXD3snrImEP5R6IHs6gGgqpnGgoZp54TDaWZkgc"
    token_type: "bearer"
    expires: 1414232110
    expires_in: 3600
    refresh_token: "X2Bxj1KzjsoaD4FCj6A0MGFWdYlGgoc31L70eSAQ"
  }

For security this access token will expire in 1 hour. We don't want the resource owner to re-accept the client every time the access token becomes invalid,
so we use the the *refresh token* to request a new one.

Request access token via refresh token:
::
  POST: auth/access_token

  Url Parms:
  grant_type    : "refresh_token"
  client_id     :  Client id
  client_secret :  Client secret
  refresh_token :  Refresh Token

Return example:
::
    {
        access_token: "n6c4Rk1lnTD3CY1lKfJVlRXvIGOH4yLhAVyf5Iz"
        token_type: "bearer"
        expires: 1414233512
        expires_in: 3600
    }

Once again this access token will expire in 1 hour. Use the refresh token from before to repeat this step whenever necessary.


Now to access the resource server on the resource owner's behalf, simply include the following header with all your requests
::
    Authorization: Bearer access_token

Ensure your Content type header is set to URL encoded.
::
    Content-Type: application/x-www-form-urlencoded


==================================
Grant: Client Credentials
==================================

The client credentials grant type allows the client itself permission to read (GET) data from the AniList API.
Reading certain current-user specific data, general editing, adding, deleting of data is not accessible from this grant type.
However this grant type doesn't require any resource owner's permission, thus is much quicker and easier to set up and use.

Request access token:
::
  POST: auth/access_token

  Url Parms:
  grant_type    : "client_credentials"
  client_id     :  Client id
  client_secret :  Client secret

Return example:
::
    {
        access_token: "NR3M3vXgHK0kmluOcJVlRXvbGOg4yLhAVyf5If"
        token_type: "bearer"
        expires: 1414234981
        expires_in: 3600
    }

You can now access the majority of the resource server's GET end points by including this access token as a "access_token" header or url parameter.
For security this access token will expire in 1 hour, to receive a new one simply repeat this step.
