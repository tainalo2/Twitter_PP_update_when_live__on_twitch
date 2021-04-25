# Twitter_PP_update_when_live_on_twitch
A free and simple way to change your twitter profile picture when you go live on twitch !

# Summary
  - Prerequesites
  - Technical explanation
  - Installation
    - Twitch API registration
    - Twitter API registration
    - Base 64 picture
    - Find your twitch ID
    - Nodered (and the infernal way to import librarie not already adapted to nodered)
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
 - Twitch API registration
   - Go to https://dev.twitch.tv/console/apps and login with your twitch account
   - Got to "Register an application", add a name to your application, and in "OAuth URL" write : "http://localhost"
   - For your application category chose "Other" and describe it (I have write : "An API to update my twitter PP by checking if I'm live")
   - Click "Create"
   - In your apllications list click "Manage"
   - Scroll down and save your "Client ID" (NEVER SHARE IT !!!)

 - Twitter API registration
   - You need to ask access to API dashboard as developper to twitter (use this link : https://developer.twitter.com/en/docs/twitter-api/getting-started/getting-access-to-the-twitter-api). It's a long process like French Bureaucracy. But after you will have all access needed instantly !
   - Once you have acces to dashboard : https://developer.twitter.com/en/portal/dashboard
   - Go to : https://developer.twitter.com/en/portal/apps/new and name your app and create it
   - Go to : https://developer.twitter.com/en/portal/projects-and-apps , find your application and click on the key icon
   - Front of "API Key and Secret", click on "Regenerate", and  save your "API Key" and "API Secret Key" (NEVER SHARE IT !!!)
   - Front of "Access Token and Secret", click on "Regenerate", and  save your "Access Token" and "Access Token Secret" (NEVER SHARE IT !!!)
   - You are the best person in the world, be brave, never forget it, it's not a satanic incantation that will stop you !

 - Base 64 picture
   - Prepare yours two profile pictures (for in live and out live) in PNG or JPG you need it in 400\*400 pixels.
   - Go on https://www.base64-image.de/ and drop your image file in
   - Click on "</>Show code"
   - Select all and saved it
   - Erased this sequence at the beginning of the base 64 code : "data:image/png;base64,"

 - Find your twitch ID
   - Go to https://www.streamweasels.com/support/convert-twitch-username-to-user-id/
   - Inform your twitch username and click "convert"
   - Save the Twitch-ID !

 - Nodered (and the infernal way to import librarie not already adapted to nodered)
   - Install twitter.js librarie to your nodered server with the next command : "npm i twitter"
   - On your server, go to the folder ".node-red"
   - Edit the "setting.js" file (With nano, the best text editor that exist)
   - Find and uncomment the "functionGlobalContext: {}," section and add next line to this section : "twitter: require('twitter')"
   - You should have something like this :
     functionGlobalContext: {
           twitter: require('twitter')
      },
   - Save and restart your nodered server with this command : "node-red-restart"

 - Nodered (and the pleasure of just import the flow and complete it)
   - Copy the content of the git file : "Nodered_flow_PP_update_when_live.json"
   - In nodered dashboard go to options and "Import"
   - Paste the file content and click "Import"
   - In the new flow go to node "function" and replace "YOUR_TWITCH_CLIENT_ID" by your twitch CLIENT-id (from de developer API plateform). Click "Done"
   - In the new flow go to node "http request" and replace "YOUR_STREAMER_ID" by your twitch Twitch-ID. Click "Done"
   - In the new flow go to node "Up_live"
   - Replace "YOUR_BASE_64_PROFILE_PICTURE_WHEN_LIVE" by your base 64 code for in live situation
   - Replace "YOUR_TWITTER_API_CONSUMER_KEY" by your twitter API Key
   - Replace "YOUR_TWITTER_API_CONSUMER_SECRET" by your twitter API Key Secret
   - Replace "YOUR_TWITTER_API_TOKEN_KEY" by your twitter Access Token
   - Replace "YOUR_TWITTER_API_TOKEN_SECRET" by your twitter Access Token Secret
   - Click "Done"
   - Do the same in node "Up_not_live" but replace the base 64 with the one for your out live profile picture
   - Click "Deploy"
   - Enjoy (as we say in french : wow tu es vraiment une belle personne !)


# Credit
Create by tainalo2 : french streamer on twitch every week day from 07H to 09H (Paris hours)
All my links here : https://linktr.ee/tainalo2
