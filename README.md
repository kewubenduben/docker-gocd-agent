# go.cd agent Docker image

Dockerfile for the [Go.cd](http://go.cd) continuous integration agent.

This builds the Go agent, you will also need [a server](https://github.com/kewubenduben/docker-gocd-server).

## Run it

    docker pull kewubenduben/docker-gocd-agent
    docker run -d -link gocd-server:server kewubenduben/docker-gocd-agent

Replace `gocd-server` in the parameter for link with the name of your gocd container,
which you can find in the last column of `docker ps`

If you're running gocd agent on a different host, simply run the agent container like so

    docker run -d kewubenduben/docker-gocd-agent -e GO_SERVER_ADDR=<HOST OF GOCD SERVER> -e GO_SERVER_PORT=<PORT SERVER LISTENING ON>