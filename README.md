# MPGame
 a 1v1 type game between two connected players in which 1 player connects via a desktop client and the other connects via webclient.
The game is presented in a different context depending on the chosen client.


For now going to use this page as a place to doccument on-going progress. I will be posting code once I figure out a good way to organize the project. 
if you have any questions or feedback for this project let me know! you can email me at mikhahmed@protonmail.com. 
i respond  to (mostly) everything lol.

# 00
![test](https://user-images.githubusercontent.com/75456828/104115281-f27bc080-52ca-11eb-83c0-c54c0f78bef9.gif)

Was able to connect my C++ backend with my frontend! The C++ server uses websockets to pass messages to and from a front-end web application made using React.
For this initial test my aim to was pass some simulated player position data at intervals of 1 second from the desktop client to the C++ server and see if it would update the web app approriately. 

The next goal will be to connect this to the "actual" Desktop game client. I have an initial multiplayer project I set-up in unreal engine 4 that I'm going to use for this. 


# 01
After some work I was able to connect both clients to the websocket server and pass data between them. for this test, i wanted to track the position of the player in the game client  within the webclient. for the actual game, i am not ever going to be sending updates this frequently so the performance now is good enough. in the gif you can also see how  objects in the 3d game client will have an abstract 2d representation in the webclient. my aim is for the web client to play from the perspective of looking down at the 3d game world. 

![test2](https://user-images.githubusercontent.com/75456828/105131285-df74a780-5aa5-11eb-91ae-eb6c79696adf.gif)

Getting to this part took a bit of work. My time was equally divided between working on the two clients and adding more functionality to the websocket server. After getting into some issues with tracking global state between different react components for the web frontend, I did some googling and learned about redux - a javascript library used to manage state. So far I gotta say that I'm a huge fan. its exactly what I needed for this project, and its made working on the frontend much easier. I've also been using the redux DevTools to view state visually during runtime. very useful tool for debugging. 


an interesting problem in this project so far has been the process of transforming 3D world coordinates to their 2D canvas coordinate equivalent. The 3D level/world is centered around (0,0,0) and has a defined bounds that is initialized prior to connection. When the websocket server detects that both clients have connected, it requests the webclient to send its current window dimensions to the game client so it can initialize a copy of them and use them to compute the transformation scale factor as needed. If the webclient ever resizes during play, it sends an update message to the websocket server containing the new window coordinates, which then passes the message to the/any connected game clients.This allows for the game to handle instances where the web-client player decides to resize their client during play. 


The next goal is to implement a system within the game client that will be responsible for sending serialized level geometry to the webclient after both clients are connected, but prior to the game-start state. The webclient will create a copy of this data and use it to render 2d abstractions of the level geometry during gameplay. 

