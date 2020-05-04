Working on turning Flask app to Quart app
Weather service needed API key. 

Needed to update global var - change from empty string to set to the key
Then looked like I needed to change from 
_api_key = api_key to the opposite ->
api_key = __api_key

This seemed to due to the trick
