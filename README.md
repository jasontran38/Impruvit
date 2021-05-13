# Impruvit

Impruvit is a habit tracking game where you and your friends can bet on doing a habit consistently. Think of it as self-improvement poker.


## MVP
3 Button bottom nav - History/Home/Profile. 
Sign up and authentication
Start with 500 points in your wallet
Ability to create a game or join a game
If joining game, a dialog box will pop up where you enter the game code to join the game lobby, where you become a spectator.
If creating a game, it will send you to a selection page where you can choose game parameters. For now we will allow stake amount to be adjusted (500, 1000, 2000). The default length and freq will be 4 weeks and daily. For now the only upload type available will be photo. After that, you will be in a lobby where you can see the game settings, and the game code which you can send to your friends for them to join (externally). As the creator of the game you can start the game or close the lobby.

There will be a "join" button you can click when you are ready to participate in the game, where you will have a prompt to enter a habit name, a short description of the habit, and a section to upload a sample proof of your habit so others can see what your habit proof will look like. This join button will turn into a "leave" button where if you click it you will turn into a spectator again. In the participation list you will see the players names, habit and thumbnail of the habit. Players can click on other player's names to see more information of the habit and a sample proof of it.

In game, the games settings section will be replaced with the game details - including yesterday's bet, today's bet, pot, stake, winnings and losses. Bet and pot will be side by side, on top of stake, winnings and losses. The players list will be identical, except the thumbnail will be replaced with grey indicating that they havent uploaded anything today. Players will be sorted by time they've uploaded their proof, and all non-uploaders will be at the bottom. The join/leave button will turn into an "Impruvit" button, where you can upload the proof for that day.

After a player has uploaded their habit for the day, the bet is revealed and the corresponding amount is added to their winnings and removed from the stake. If the habit hasn't been uploaded by 00:01 the following day, the bet amount will be added to the pot, and added to the losses and removed from stake. 

At the end of the game, the players will be sorted by days of the habit completed, which will be shown in the thumbail. The game stats will show the pot and number of winners. The "Impruvit" button will be an exit button, which once they press will update their external wallet to reflect how much they won back. 

---
### Home
Home shows a create game button and a join button. Create game sends you to a game activity flow, where you enter game parameters and then you enter a game lobby where you get a game code. On our end, this is when we select a bet distribution for the game. For others to join this game, they click on the join game button and enter this code. 

#### Lobby
In the game lobby, players see the game settings, which includes the number of players, buy-in (stake amount + entry fee) and guaranteed pot (half of the entry fees; the other half goes to us). There will be a button to either leave the game or pledge. 

To pledge, a player enters a title, description and a sample upload of the type of habit they'll be doing so other players know what to expect in terms of your proof. A good guideline is something that cannot be faked, e.g. Photo of date on watch with a gym in the background. At this point, the stake and fee will be removed from their wallet and they will not be able to exit. Players will get a confirmation to let them know this.

Users will see all of the players who have pledge in a list with their name and habit. A player can click on themselves or another player to see the full description and proof.

#### Game start
When all players have pledged, the game will officially start on 00:01 the next day. Everyday, the bet for that day is chosen. A player needs to upload their proof for that they to find out and win that bet back. Otherwise, the bet is hidden until they do. This repeats the day after, and everyone who failed that bet the day before has their bet added to the pot. 

The ingame screen will look similar to the lobby, except it shows the bet, losses (money lost), and win (days won - colour will represent streaks: 0). All the players will be in a list with their name and a story thumbnail. It is empty before they upload, and it will show a thumbnail of their upload and move them to the top of the list. A player can tap on someones name to see their pledge, or the thumbnail to see their upload. 

#### Game end
The winner(s) will be whoever uploaded the most. Winner takes all (or split between winners if their is a tie). At the end, the ultimate winner is revealed by having a crown in their upload story, and everyone else will have poop. Players can see their overall performances by tapping on their name, which will show how much money they won/loss, how many days they completed, and a calendar of their progress in that month, e.g. similar to most other habit trackers.  

### History
History shows a list of previous games, of which when you tap on it it shows a summary of the end game screen of that game.
