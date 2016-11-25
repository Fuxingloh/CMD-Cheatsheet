## Dockerfile

```bash
FROM user/project:tag # From what base image (this is a must)
MAINTAINER Your Name <example@website.com> # Information about the mainter 

ARG NAME=something

VOLUME ["/data"] # set volume
WORKDIR /src # set current working directory to /src

ADD http://something.com /usr/html/file # copy a file from a url to that directory
ADD src/ /usr/html/ # copy a directory and move to container

COPY src/ /usr/html/  # copy a directory and move to container
COPY nginx.conf /etc/nginx/nginx.conf # copy a file and move to container

EXPOSE 8000 # expose port 8000 to outside

ENV API_KEY some thing # set the environment variable
ENV PROD_DOMAIN="http://www.com" NODE_ENV="production"

CMD ["node", "bin/www"] # basically running a cmd, in this case, running a program with parameters
```
