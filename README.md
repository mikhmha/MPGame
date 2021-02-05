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


# 05/02/2021 Update
Still working on this project. Most of the recent work has been focused on the backend trying to design a good framework for coordinating the game state between the different clients. I've also been toying with the idea of allowing mutliple UE4 clients and web-clients to play together so the game can be scaled up from 1v1 to NvM. 

