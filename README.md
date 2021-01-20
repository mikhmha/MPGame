# MPGame
Repo for a multiplayer game concept I am trying to protype.
The concept is a 1v1 type game between two connected players in which 1 player connects via a desktop client and the other connects via webclient.
The game is presented in a different context depending on the chosen client.


For now going to use this page as a place to doccument on-going progress. I will be posting code once I figure out a good way to organize the project.

Initial Milestone:
![test](https://user-images.githubusercontent.com/75456828/104115281-f27bc080-52ca-11eb-83c0-c54c0f78bef9.gif)

Was able to connect my C++ backend with my frontend! The C++ server uses websockets to pass messages to and from a front-end web application made using React.
For this initial test my aim to was pass some simulated player position data at intervals of 1 second from the desktop client to the C++ server and see if it would update the web app approriately. The  web context for this game is going to be built around non-real-time gameplay, so getting real-time performance isn't a huge concern. So far everything looks good. 

The next goal will be to connect this to the "actual" Desktop game client. I have an initial multiplayer project I set-up in unreal engine 4 that I'm going to use for this. 


![test2](https://user-images.githubusercontent.com/75456828/105131285-df74a780-5aa5-11eb-91ae-eb6c79696adf.gif)
