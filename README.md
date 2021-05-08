# Impruvit

Impruvit is a habit tracking game where you and your friends can bet on doing a habit consistently. Think of it as self-improvement poker.

MVP
Sign up and authentication
Start with 500 points in your wallet
Ability to create a game or join a game
If joining game, a dialog box will pop up where you enter the game code to join the game lobby, where you become a spectator.
If creating a game, it will send you to a selection page where you can choose game parameters. For now we will allow stake amount to be adjusted (500, 1000, 2000). The default length and freq will be 4 weeks and daily. For now the only upload type available will be photo. After that, you will be in a lobby where you can see the game settings, and the game code which you can send to your friends for them to join (externally). As the creator of the game you can start the game or close the lobby.

There will be a "join" button you can click when you are ready to participate in the game, where you will have a prompt to enter a habit name, a short description of the habit, and a section to upload a sample proof of your habit so others can see what your habit proof will look like. This join button will turn into a "leave" button where if you click it you will turn into a spectator again. In the participation list you will see the players names, habit and thumbnail of the habit. Players can click on other player's names to see more information of the habit and a sample proof of it.

In game, the games settings section will be replaced with the game details - including yesterday's bet, today's bet, pot, stake, winnings and losses. Bet and pot will be side by side, on top of stake, winnings and losses. The players list will be identical, except the thumbnail will be replaced with grey indicating that they havent uploaded anything today. Players will be sorted by time they've uploaded their proof, and all non-uploaders will be at the bottom. The join/leave button will turn into an "Impruvit" button, where you can upload the proof for that day.

After a player has uploaded their habit for the day, the bet is revealed and the corresponding amount is added to their winnings and removed from the stake. If the habit hasn't been uploaded by 00:01 the following day, the bet amount will be added to the pot, and added to the losses and removed from stake. 

At the end of the game, the players will be sorted by days of the habit completed, which will be shown in the thumbail. The game stats will show the pot and number of winners. The "Impruvit" button will be an exit button, which once they press will update their external wallet to reflect how much they won back. 
