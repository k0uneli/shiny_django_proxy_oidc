# Docker example with NginX + Auth-Request module proxying to auth-acting Django server for Shiny app
This is a Docker setup for a Django application acting as an authentication
and authorization server for a Shiny application, through the NginX
reverse-proxy and auth-request module. This is an adapation of docker-nginx-auth-request-django-shiny-example but using mozilla-django-oidc instead of the default django auth, and also updated as the original codebase is over half a decade old and doesn't work anymore.

- We use NginX as reverse proxy.
- We use mozilla-django-oidc to manage auth with SSO. Eventually the aim is to link it with AAF but right now it is used with auth0
- The initial Shiny application main page is wrapped into a
  Django-powered page, so we can build an interface above Shiny,
  with user and access rights management.
- Currently the shiny app is just an example app, next step is to integrate the dashboard app.

## Requirements
You need to install Docker and Docker-Compose.

## Build
`sudo make all`.

## Run
`sudo make up`.

## Help
`make` or `make help`.

## Note
Ensure you do not put the SSO server key in version control! keep it in the environment and use os.environ :)
