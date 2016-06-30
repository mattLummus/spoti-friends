# Premise and Architetcure

### Premise

* Spoti-Friends is an app that lets friends co-operatively listen to music as a social experience. One streaming service, where multiple people can control and listen to at the same time.
* Users create groups, which is a collection of users with one "stream". When one is subscribed to the Stream. 

#### Architecture

* Spoti-Friends V1 is built leveraging the Spotify API, embeddable player, and web technologies such as Javascript and sockets for syncing.
* A group contains data such as a current playing track, a queue of what is to come, and sync info.
* This is published to client consumers (i.e. through a browser) who then use it to run the experience.
* On load, the Script takes the current track, loads it through an embeddable player, info about the queue, and then programatically updates the player to sync with the group.
* When a change is made, this is published to consumers via socket connections.
* **In V2, one consumer will attempt to always act as host, which will stream audio directly captured from the player and broadcast to others in the group. If host leaves, another will pick up responsibility**
