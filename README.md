# Twitter_PP_update_when_live_on_twitch
A free and simple way to change your twitter profile picture when you go live on twitch !

# Summary
  - Prerequesites
  - Technical explanation
  - Installation
    - Twitch API registration
    - Twitter API registration
    - Base 64 picture 
    - Nodered (and the infernal way to import librarie not already adapt to nodered)
    - Nodered (and the pleasure of just import the flow and complete it)
  - Credit

# Prerequesites
  - A nodered server (free low code GUI for NodeJS server) https://nodered.org/

# Technical explanation
The objective is to update the twitter profile picture when you are streaming on your channel twitch
  - A default twitch channel status is saved in the nodered flow
  - A nodered node is checking every minute the status of the twitch channel over twitch API
  - If status is different than the saved status, the new profile picture is upload over twitter API
  - Else the nodered flow is stopped

# Installation
 - SOON
 

# Credit
Create by tainalo2 : french streamer on twitch every week day from 07H to 09H (Paris hours)
All my links here : https://linktr.ee/tainalo2
