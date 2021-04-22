# MPGame
 a 1v1 type game between two connected players in which 1 player connects via a desktop client and the other connects via webclient.
The game is presented in a different context depending on the chosen client.


For now going to use this page as a place to doccument on-going progress. I will be posting code once I figure out a good way to organize the project. 
if you have any questions or feedback for this project let me know! you can email me at mikhahmed@protonmail.com. 


# 00
![test](https://user-images.githubusercontent.com/75456828/104115281-f27bc080-52ca-11eb-83c0-c54c0f78bef9.gif)

Was able to connect my C++ backend with my frontend! The C++ server uses websockets to pass messages to and from a front-end web application made using React.
For this initial test my aim to was pass some simulated player position data at intervals of 1 second from the desktop client to the C++ server and see if it would update the web app approriately. 

The next goal will be to connect this to the "actual" Desktop game client. I have an initial multiplayer project I set-up in unreal engine 4 that I'm going to use for this. 


# 01
After some work I was able to connect both clients to the websocket server and pass data between them. for this test, i wanted to track the position of the player in the game client  within the webclient. for the actual game, i am not ever going to be sending updates this frequently so the performance now is good enough. in the gif you can also see how  objects in the 3d game client will have an abstract 2d representation in the webclient. my aim is for the web client to play from the perspective of looking down at the 3d game world. 

![test2](https://user-images.githubusercontent.com/75456828/105131285-df74a780-5aa5-11eb-91ae-eb6c79696adf.gif)


Getting to this part took a bit of work. My time was equally divided between working on the two clients and adding more functionality to the websocket server. After getting into some issues with tracking global state between different react components for the web frontend, I did some googling and learned about redux.


# 05/02/2021 Update
Still working on this project. Most of the recent work has been focused on the backend trying to design a good framework for coordinating the game state between the different clients. I've been toying with the idea of allowing mutliple UE4 clients and web-clients to play together so that the game can be scaled up from 1v1 to NvM (UE4 clients vs Webclients). 


# update
my pc shuts off after <10 min use so development is stopped for a bit. i ordered a new PSU so hopefully that solves the issue, otherwise im pretty sure the problem is the motherboard.

some of the stuff ive done for this project is also being used in my HFT project so follow that if you find this project interesting. in many ways its not too different from this project but the focus is on real-time finance data visualization rather than game stuff. Looking to get that project live soon (if new psu keeps my pc alive).

# update

i haven't had much time to commit to this project. i'm still interested in working on it, though i'm in no rush. maybe one day~

some more context for the game:
- it was/is going to be a stealth/heist multiplayer game
- the player in the browser would basically play the role of a dungeon master - they have a birds eye view of the level and can deploy/schedule resources to locate and impede the other players progress
- other player (UE4 client) is basically playing a 3D real-time game where they have to succesfully navigate through a level while evading the watchful gaze of the dungeon master
- the dungeon master wouldn't always have a visual on the other players location. they can utilize resources to reveal the player location for short periods of time. resources could be stuff like dropping radar in a small region for a period of time, or a full map scan. resources could be on cool downs or limited to X uses per round.
- the game would be built around latency and asynchronous networking

# Why make one player play through browser?

Technically I could just skip the browser and build the dungeon master concept in UE4. It'd be way less work, I'd be able to use the same level asset and all I'd have to do is  change the view perspective for the other player. I wouldn't have to mess around with all the extra client/server websocket stuff.

 I decided to build this for the web instead because I thought it'd be a cool and novel idea. What I've seen with asynchronous multiplayer games is that usually one role is vastly preferred more than the other. Most players don't like playing the role of the DM (not for long atleast). By making the DM role of the game very easy to try, I figured it would help with this issue. 

Also I think it'd be effective from an advertising perspective. Say that someone stumbles upon the site, and ends up playing as the DM a few times. If they get some entertainment out if it maybe that encourages them to download the game on steam to experience the other half of it?

