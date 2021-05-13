# Impruvit

Impruvit is a habit tracking game where you and your friends can bet on doing a habit consistently. Think of it as self-improvement poker.


## MVP
For me and the boys

### Authentication
Will use firebase auth.

### Home
Home shows a create game button and a join button, as well as user's coins. Create game sends you to a game activity flow, where you enter game parameters. For others to join this game, they click on the join game button and enter the game code (below). Players can only join if they have enough coins in the wallet to cover the buyin.

### Parameters
In the game parameter dialog, you can select: val total buy-in (550, 1100, 2200), val numPlayers. The game has hardcoded parameters for length (30 days), frequency (daily) and proof type (photo). User can then click start lobby to initialize the lobby, with those parameters, along with var currLobbySize (if 0, delete lobby), and var numPledged (if == numPlayers start countdown). On our end, this is when we select a bet distribution for the game (list of int).

### Lobby
In the game lobby, players see the game settings, which includes the number of players, stake amount, guaranteed pot and game code. There will be a button to either leave the game or pledge. 

Users will see all of the players who have pledged in a list with their name and habit title. A player can click on themselves or another player to see the full description and proof. When all players have pledged, a countdown will begin until 00:01 the next day, which is when the game will start. A player can leave and rejoin if they want to do a different pledge. 

### Confirmation
To pledge, a player enters a title, description and a sample upload of a habit they'll be doing so other players know what to expect in terms of proof. A good guideline is something that cannot be faked, e.g. Photo of date on watch with a gym in the background. 

### In-game
On game start, the buy in will be removed from everyone's wallet. Everyday, the bet for that day is chosen, but hidden. The bet is a fraction of the stake such that all bets over the game equal the stake. A player needs to upload proof for their chosen habit to reveal and win the bet. They must do this before 00:01 the next day, or else their bet will be added to the pot, e.g. if player.upload == null: player.stake -= bet, player.loss += bet, pot += bet.

In game, the games settings section will be replaced with the game details - including yesterday's bet, today's bet, pot, current stake, total losses (money), and days completed. Bet and pot will be side by side, on top of stake, winnings and losses. The players list will be identical, except the thumbnail will be replaced with grey indicating that they havent uploaded anything today. The leave button will turn into an "Impruvit" button, where you can upload the proof for that day. A player can tap on someones name to see their pledge, or the thumbnail to see their upload in the form of a "snap story" 

### Upload flow
On upload, launch the pledge fragment but with the proof box empty to signal upload. On return, reveal bet, remove bet from stake, turn player status bar green, and set user story to the thumbnail of upload. player.stake -= bet, player.win += bet.

### Game end
The winner(s) will be whoever won the most days. Winner takes all (or split between winners if there is a tie). At the end, the ultimate winner is revealed by having a crown in their upload story, and everyone else will have poop. Players can see their overall performances by tapping on their name, which will show how much money they netted overall and how many days they completed. The game stats will show the pot and number of winners. The "Impruvit" button will be an exit button, which once they press will update their external wallet to reflect how much they won back. 

### Profile
There will be a profile button where you can buy coins. They can enter the secret code to fill up their coins up to 550. There will also be a help button which runs through how to play the game, FAQs, etc.

----
Next Version, padding out the MVP so it isn't just the literal bare minimum. E.g. A Minimalist Product, not a Minimal Viable Product.

Major Update:

### XP
Earn XP (absolute measure of work) as compared to coins (relative value). In more expensive games, XP multiplier increases. XP can go towards unlocking titles from the skill tree, coins unlock ranks (e.g. bronze game = $500, 200XP max, 50XP middle\ silver game = $1000, 500XP max, 200XP middle\ gold game = $2000, 1500XP max, 500XP middle\ diamond = $4000, 4000XP max, 1500XP middle). This will also be good to offset when most people win in a game - they will get more XP to compensate for lower pot. And vice versa. 


### Lobby
In the game lobby, players see the game settings, which includes the number of players, stake amount, and guaranteed pot (half of the entry fees; the other half goes to us). There will be a button to either leave the game or pledge. 

To pledge, a player enters a title, description and a sample upload of 2 habits they'll be doing so other players know what to expect in terms of your proof. Remember, you're trying to win at the same time as making them lose. So make your chosen habit that you want to build easy enough to do, but the other one hard for others to do (so you have 1 habit you're trying to "normalise" and another habit that is almost outside the bounds of your capibility, which will be hard for yourself but even harder for everyone else).

Users will see all of the players who have pledge in a list with their name and 2 habits. A player can click on themselves or another player to see the full description and proof. When all players have pledged, a countdown will begin until 00:01 the next day, which is when the game will start.

### Game start
When all players have pledged, the game will officially start on 00:01 the next day. Everyday, the bet and a habit for that day is chosen, but hidden. A player needs to upload proof for their chosen habit to reveal the hidden bet and habit. They can then choose to upload the other habit to win the bet. They must do this before 00:01 the next day, or else their bet will be added to the pot. 

The ingame screen will look similar to the lobby, except it shows the pot, current stake, today's bet and yesterday's bet (in red or green depending if they won it or lost it), losses (money lost), and days won. All the players will be in a list with their name and a story thumbnail. They are empty before they upload, and their bar will be grey. Upon the first upload, the story will show the thumbnail, turn their bar yellow and move them to the top of the list. Upon the second, it will turn their bar green and move them to the top again. A player can tap on someones name to see their pledge, or the thumbnail to see their upload. The most recent upload will be shown first. Players can only see uploads of other players once they've done their first upload. This incentivises players to upload their first one because of the possibility that others will cheat of they don't (since they have no way to tell).

### Game end
They will also see how much XP they won at the end of the game. The more days completed, the more XP is won, which can go towards their level and title. Players can also see 
a calendar of their progress in that game, e.g. similar to most other habit trackers.  

### Profile
In the buy menu, there will be 3 options: 50, 150, and 500 for $50, $100, and $200 respectively.

There will be a history button which shows a list of previous games, of which when you tap on it it shows a summary of the end game screen of that game. It will be identical to the end game screen when you were actually at the end of a game. 

We also have Privacy Policy, Feedback, Rating, Terms and Conditions, etc. 

---


