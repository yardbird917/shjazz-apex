# Apex Legends Twitch Bot

Apex Legends chat command for any Twitch.tv bot that has a an URI fetch command system.

**Works with:** *[Nightbot, Ankhbot, Deepbot](https://blog.thomassen.xyz/custom-apis/), Phantombot and probably more unknown.* 

Apex Legends Twitch streamers, this is a PHP script that uses the API statistics and gathers end-points of the Apex Legends Rank stats and forwards them to [Nightbot](http://nightbot.tv).

This server-side script is making use of Nightbot's dynamic response system (mostly [$(urlfetch)](https://docs.nightbot.tv/commands/variables/urlfetch)) with which you are able to fetch the resources forwarded by my Heroku App.

Do not worry! Nothing is saved server-side.

## How to add commands to Nightbot

With chat:  
["!commands add !command_name command_response"](https://docs.nightbot.tv/commands/commands)  
With interface:  
https://beta.nightbot.tv/commands/custom  

Here's what the response should contain for Nightbot to reply with your current rank:  

    $(urlfetch http://yourservername.herokuapp.com/apexstats.php?platform=YourPlatformHere&nick=YourNickHere&command=rank)
- Adjust the URL parameters to fit your purposes.
- ?platform= *(xbl, psn or origin.)*  
**xbl** for Xbox One,   
**psn** for PS4,  
**origin** for PC.  

- &nick= *(Your username on the specific platform.)*
- Specify a command after the *&command=* query parameter at the end of the URL in the $(urlfetch) method.   
In the example above I specified "*rank*" as for the current rank in the current season.  

Note:  
- **You CAN write custom text before and after $(urlfetch) in the response!**  
- Do NOT forget to close any opening parantheses '(' with a closing ')' at the end!  
- You can let the user search for a player himself by doing *?platform=$(1)&nick=$(2)*.
The user will have to put a platform and a nick as arguments separated by a space after your command.


## Deployment to Heroku

replace **$apikey = '';** in **apexstats.php** your api key. [GET API KEY HERE](https://api.mozambiquehe.re/getkey)


    $ git init
    $ git add -A
    $ git commit -m "Initial commit"

    $ heroku create
    $ git push heroku master

    $ heroku run python manage.py migrate

See also, a [ready-made application](https://github.com/heroku/python-getting-started), ready to deploy.

or fork this repo and press

<p><a href="https://heroku.com/deploy" rel="nofollow"><img src="https://camo.githubusercontent.com/c0824806f5221ebb7d25e559568582dd39dd1170/68747470733a2f2f7777772e6865726f6b7563646e2e636f6d2f6465706c6f792f627574746f6e2e706e67" alt="Deploy to Heroku" data-canonical-src="https://www.herokucdn.com/deploy/button.png" style="max-width:100%;"></a></p>

## Credit

**Giuthub** https://github.com/HugoDerave/ApexLegendsAPI

**Discord** https://discord.gg/TZ4Y9EB


