# Shinycker
### Template for Dockerized Shiny (R\) application

This is a Dockerfile for Shiny Server based on `r-base` image.

## Usage:

To build an image with specific packages for your app:
```sh
docker build 
```

To run a temporary container with your_app that store your logs on `logs/`:

```sh
docker run -d -p 80:80 
    -v logs/:/var/log/shiny-server/ \
    your_app 
```


### Logs

The Shiny Server log and all application logs are written to `stdout` and can be viewed using `docker logs`.

The logs for individual apps are still kept in the `/var/log/shiny-server` directory, as described in the [Shiny Server Administrator's Guide]( http://docs.rstudio.com/shiny-server/#application-error-logs). 

## Acknowledgement
This repo exists because other people helped in the process:
- [Learn How to Dockerize a ShinyApp in 7 Steps · Björn Bos](https://www.bjoern-hartmann.de/post/learn-how-to-dockerize-a-shinyapp-in-7-steps/) by [bjoernbos](https://github.com/bjoernbos)
- [GitHub - rocker-org/shiny](https://github.com/rocker-org/shiny)
