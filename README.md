# Game:
larpit.netlify.app

## I will inform game owner

## Pentested Vulns:

#### Game puts too much trust on clients

#### Game puts all possible words on client side

#### Multiplayer game Databased exposed:
https://gamenight-34130-default-rtdb.firebaseio.com/larpit/[ROOMCODE].json

## Demos

### anti_larp

`anti_larp.html` is a deduction engine made by the fact that all the words are on the client side, therefore in a non-multiplayer, single device game, the larper can have this open to deduct the words that don't make sense, resulting in a elevated chance of victory as a larper.

### Reality room

`reality_room_intel.html` is a database intelligence engine, because the multiplayer game database is exposed, anyone can see everything. In a multiplayer game, all the larper has to do is to open up this page, type the roomcode and then they have the word, resulting in an instant victory as a larper.

### Others

There are so many vulnerabilities because of client side logic, that you can simply control the MULTIPLAYER game with client side inspect element console. All you have to do is open the JS console and start running any functions of your choosing. I wont bother to write tools for this.
