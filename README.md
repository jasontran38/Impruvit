# Impruvit

Impruvit is a habit tracking game where you and your friends can bet on doing a habit consistently. Think of it as self-improvement poker.


## MVP
For me and the boys

3 Button bottom nav - History/Home/Profile. 
Sign up and authentication
Start with 500 points in your wallet
Ability to create a game or join a game
If joining game, a dialog box will pop up where you enter the game code to join the game lobby, where you become a spectator.
If creating a game, it will send you to a selection page where you can choose game parameters.  After that, you will be in a lobby where you can see the game settings, and the game code which you can send to your friends for them to join (externally). As the creator of the game you can start the game or close the lobby.

There will be a "join" button you can click when you are ready to participate in the game, where you will have a prompt to enter a habit name, a short description of the habit, and a section to upload a sample proof of your habit so others can see what your habit proof will look like. This join button will turn into a "leave" button where if you click it you will turn into a spectator again. In the participation list you will see the players names, habit and thumbnail of the habit. Players can click on other player's names to see more information of the habit and a sample proof of it.

In game, the games settings section will be replaced with the game details - including yesterday's bet, today's bet, pot, stake, winnings and losses. Bet and pot will be side by side, on top of stake, winnings and losses. The players list will be identical, except the thumbnail will be replaced with grey indicating that they havent uploaded anything today. Players will be sorted by time they've uploaded their proof, and all non-uploaders will be at the bottom. The join/leave button will turn into an "Impruvit" button, where you can upload the proof for that day.

After a player has uploaded their habit for the day, the bet is revealed and the corresponding amount is added to their winnings and removed from the stake. If the habit hasn't been uploaded by 00:01 the following day, the bet amount will be added to the pot, and added to the losses and removed from stake. 


---
### Authentication
Will use firebase auth.

### Home
Home shows a create game button and a join button, as well as user's coins. Create game sends you to a game activity flow, where you enter game parameters. For others to join this game, they click on the join game button and enter this code. Players can only join if they have enough coins in the wallet to cover the buyin.

In the game parameter dialog, you can select: total buy-in (550), num players.
Start lobby creates lobby, with currLobbySize (if 0, delete lobby), and numPledged. On our end, this is when we select a bet distribution for the game.
For now we will allow stake amount to be adjusted (550, 1100, 2200). The default length and freq will be 4 weeks and daily. For now the only upload type available will be photo.
#### Lobby
In the game lobby, players see the game settings, which includes the number of players, stake amount, guaranteed pot and game code. There will be a button to either leave the game or pledge. 

To pledge, a player enters a title, description and a sample upload of a habit they'll be doing so other players know what to expect in terms of proof. A good guideline is something that cannot be faked, e.g. Photo of date on watch with a gym in the background. 

Users will see all of the players who have pledge in a list with their name and habit title. A player can click on themselves or another player to see the full description and proof. When all players have pledged, a countdown will begin until 00:01 the next day, which is when the game will start. A player can leave and rejoin if they want to do a different pledge. 

#### Game start
The game will officially start on 00:01 the next day, when the buy in will be removed from everyone's wallet. Everyday, the bet for that day is chosen, but hidden. The bet is a fraction of the stake such that all bets over the game equal the stake. A player needs to upload proof for their chosen habit to reveal and win the bet. They must do this before 00:01 the next day, or else their bet will be added to the pot. 

The ingame screen will look similar to the lobby, except it shows the bet along with the rest of the game details. All the players will be in a list with their name and a story thumbnail. They are empty before they upload, and their bar will be grey. Upon the upload, the story will show the thumbnail, their bar will turn their bar green and move them to the top of the list. A player can tap on someones name to see their pledge, or the thumbnail to see their upload.

#### Game end
The winner(s) will be whoever won the most days. Winner takes all (or split between winners if there is a tie). At the end, the ultimate winner is revealed by having a crown in their upload story, and everyone else will have poop. Players can see their overall performances by tapping on their name, which will show how much money they netted overall and how many days they completed. The players will be sorted by days of the habit completed. The game stats will show the pot and number of winners. The "Impruvit" button will be an exit button, which once they press will update their external wallet to reflect how much they won back. 

#### Profile
There will be a profile button where you can buy coins. There will be 3 options: 50, 150, and 500 for $50, $100, and $200 respectively, or they can enter the secret passcode to fill up their coins up to 550. There will also be a help button which runs through how to play the game, FAQs, etc.

----
Next Version, padding out the MVP so it isn't just the literal bare minimum. E.g. A Minimalist Product, not a Minimal Viable Product.

Major Update:

#### Lobby
In the game lobby, players see the game settings, which includes the number of players, stake amount, and guaranteed pot (half of the entry fees; the other half goes to us). There will be a button to either leave the game or pledge. 

To pledge, a player enters a title, description and a sample upload of 2 habits they'll be doing so other players know what to expect in terms of your proof. A good guideline is something that cannot be faked, e.g. Photo of date on watch with a gym in the background. Remember, you're trying to win at the same time as making them lose. So make your chosen habit that you want to build easy enough to do, but the other one hard for others to do (so you have 1 habit you're trying to "normalise" and another habit that is almost outside the bounds of your capibility). At this point, the stake and fee will be removed from their wallet and they will not be able to exit. Players will get a confirmation to let them know this.

Users will see all of the players who have pledge in a list with their name and 2 habits. A player can click on themselves or another player to see the full description and proof. When all players have pledged, a countdown will begin until 00:01 the next day, which is when the game will start. On our end, this is when we select a bet distribution for the game.

#### Game start
When all players have pledged, the game will officially start on 00:01 the next day. Everyday, the bet and a habit for that day is chosen, but hidden. A player needs to upload proof for their chosen habit to reveal the hidden bet and habit. They can then choose to upload the other habit to win the bet. They must do this before 00:01 the next day, or else their bet will be added to the pot. 

The ingame screen will look similar to the lobby, except it shows the bet, losses (money lost), and win (days won - colour will represent streaks: 0). All the players will be in a list with their name and a story thumbnail. They are empty before they upload, and their bar will be grey. Upon the first upload, the story will show the thumbnail, turn their bar yellow and move them to the top of the list. Upon the second, it will turn their bar green and move them to the top again. A player can tap on someones name to see their pledge, or the thumbnail to see their upload. The most recent upload will be shown first. Players can only see uploads of other players once they've done their first upload. This incentivises players to upload their first one because of the possibility that others will cheat of they don't (since they have no way to tell).


History shows a list of previous games, of which when you tap on it it shows a summary of the end game screen of that game. They will also see how much XP they won at the end of the game. The more days completed, the more XP is won, which can go towards their level and title.

Upon tapping a player's name, show a calendar of their progress in that game, e.g. similar to most other habit trackers.  
Privacy Policy, Feedback, Rating, Terms and Conditions, etc. 
Earn XP (absolute measure of work) as compared to coins (relative value). In more expensive games, XP multiplier increases. XP can go towards unlocking titles from the skill tree, coins unlock ranks (e.g. bronze game = $500, 200XP max, 50XP middle\ silver game = $1000, 500XP max, 200XP middle\ gold game = $2000, 1500XP max, 500XP middle\ diamond = $4000, 4000XP max, 1500XP middle). This will also be good to offset when most people win in a game - they will get more XP to compensate for lower pot. And vice versa. 
