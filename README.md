# Fly + Create React App = ❤️

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

This serves as a simple way to teach React developers how to deploy on Fly.io

## How to deploy this?

If you just want to deploy this project all you need is `fly launch` and accept copying the configuration.

```sh
$ fly launch
An existing fly.toml file was found
? Would you like to copy its configuration to the new app? Yes
Creating app in /path/to/fly-create-react-app
Scanning source code
Detected a Dockerfile app
? App Name (leave blank to use an auto-generated name): create-react-app-on-fly
? Select organization: Lubien (personal)
? Select region: gru (São Paulo)
Created app create-react-app-on-fly in organization personal
Wrote config file fly.toml
? Would you like to set up a Postgresql database now? No
? Would you like to deploy now? Yes
Deploying create-react-app-on-fly
==> Validating app configuration
--> Validating app configuration done
...
```

## How to add this to my other React project?

The important files here are the Dockerfile, `fly.toml`, `.dockerignore` and the `nginx` folder.

Copy those to your project and you should be good to go.

## How does this work?

This setup uses a Dockerfile with NodeJS to build your project using `npm run build` then we copy the built files
to a Nginx image to serve all statics handling pretty URLs.

Worth mentioning we added `[[statics]]` to the `fly.toml` to cache statics too.