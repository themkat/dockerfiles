FROM debian:stretch-slim

	# TODO: remove cache to get a smaller image.And probably other optimizations as well if possible
# The dpkg command will fail because of dependencies, but will be installed with the apt-get install command.
RUN apt-get update && \
	apt-get install -y wget libx11-xcb-dev --no-install-recommends  && \
	wget --no-check-certificate -O discord.deb "https://discordapp.com/api/download?platform=linux&format=deb" && \
	apt-get install -y ./discord.deb && \
	rm discord.deb

# TODO: fix the issue with the container just exiting
#ENTRYPOINT ["discord"]
