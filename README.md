# laravel-auth0

## Source

This is based from [Build and Secure a Laravel API](https://auth0.com/blog/build-and-secure-laravel-api)

## Configuration

Just create your database:

```
touch database/database.sqlite
```

And add the following parameters in your .env:

```
DB_CONNECTION=sqlite
DB_DATABASE=/absolute/path/to/database.sqlite

AUTH0_DOMAIN=your-domain.auth0.com
API_IDENTIFIER=https://your-api.com
AUTH0_CLIENT_ID=
```

(See the tutorial above to understand where to find those values in the auth0 dashboard)

## Notes

The only thing I changed to avoid an error if you don't put the Authorization Bearer token is the following code at the line 36 of app/Http/Middleware/CheckJWT.php

```
  if (!$accessToken) {
    return response()->json(["message" => "No token was found"], 401);
  }
```
