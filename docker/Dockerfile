
# Based on <github.com/tobiashutterer>
FROM node:6.2.2
MAINTAINER Dmitri Sakara
ENV NODE_ENV development
# defining a user because polymer-cli doesn't like root user!
ENV USER polymer
RUN apt-get update
RUN apt-get -y install sudo
# to skip password prompt for sudo users
RUN echo %sudo ALL=NOPASSWD: ALL >> /etc/sudoers
# setting up a user
RUN useradd --create-home --shell /bin/bash $USER && adduser $USER sudo
ENV HOME /home/$USER
WORKDIR $HOME
# making the $USER owner of node_modules dir to avoid permission errors
RUN chown -R $USER /usr/local/lib/node_modules/
RUN npm install -g bower grunt-cli gulp

# switching to the non-root user
USER $USER
RUN sudo npm install -g polymer-cli
RUN npm cache clear
EXPOSE 8080
CMD ["/bin/bash"]

# Install
# docker run --name polymer-dev -it -d -p 8080:8080 -v test1:/home/polymer/test1 dms/polymer-dev:latest

# Create and run polymer-dev container (includes port forwarding and folder mapping)
# docker run --name polymer-dev -it -d -p 8080:8080 -v /Users/Dmitri/projects/exp2/test1:/home/polymer/test1 dms/polymer-dev:latest

# Re-start polymer-dev container
# docker start polymer-dev

# Connect
# docker exec -it polymer-dev bash