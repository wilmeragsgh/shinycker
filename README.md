# Shinycker
### Template for Dockerized Shiny (R\) application

This is a Dockerfile for Shiny Server based on `r-base` image, including some basic functional conf file for the container.

## Usage:

To build an image with specific packages your_pkgs ( e,g: `\'shinydashboard\',\'plotly\'` with explicit `\'` :point_left: ) for your_app:
```sh
docker build -t your_app \
    --build-arg add_pkg=your_pkgs \
    --no-cache .
```

To run a temporary container with your_app that store your logs on `logs/`:

```sh
docker run -d -p 80:80 
    -v logs/:/var/log/shiny-server/ \
    -v your_app/:/srv/shiny-server/ \
    your_app 
```


### Logs

The Shiny Server log and all application logs are written to `stdout` and can be viewed using `docker logs`.

The logs for individual apps are still kept in the `/var/log/shiny-server` directory, as described in the [Shiny Server Administrator's Guide]( http://docs.rstudio.com/shiny-server/#application-error-logs). 

## Acknowledgement
This repo exists because other people helped in the process:
- [Learn How to Dockerize a ShinyApp in 7 Steps · Björn Bos](https://www.bjoern-hartmann.de/post/learn-how-to-dockerize-a-shinyapp-in-7-steps/) by [bjoernbos](https://github.com/bjoernbos)
- [GitHub - rocker-org/shiny](https://github.com/rocker-org/shiny)
