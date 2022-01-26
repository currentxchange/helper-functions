# Helper Functions
Functions to help your app work with cXc.world 🌎


```javascript
// --- Returns the current Time Unit --- \\
function getTu() { // Returns the current Time Unit
  // 1561139700 is the first Time Unit
  let nowts = new Date().getTime(); 
  let tu_ = Math.floor((Math.floor(nowts/1000) - 1561139700) / 300);  // Divide by the length of a Time Unit in seconds
  return tu_;
}//END getTu()


// --- Calculate Everstone rewards based upon Staked PURPLE --- \\
function rewardCalc(staked = 0){ 
  if (staked < 1){return 0;}
  staked = parseInt(staked);
  let levels = [1,2,3,4,8,12,16,32,64,999999];
  let rewards = [1,3,5,7,16,30,48,144,432];
  for (var i = 0; i < levels.length; i++) {
    if (staked < levels[i])
    {
      return rewards[i-1];
      break;
    }
  }
}//END rewardCalc


// --- Calculate Solar Disk rewards based upon Staked PURPLE --- \\
function rewardCalcSolar(staked = 0){
  staked = parseInt(staked);
  if (staked < 1){return 0;}
  let levels = [1,2,3,4,8,12,16,32,64,128,192,256];
  let rewards = [24,48,72,96,120,144,168,192,216,240,264,288];
  for (var i = 0; i < levels.length; i++) {
    if (staked < levels[i])
    {
      return rewards[i];
      break;
    }
  }
}//END rewardCalcSolar

// --- Calculate Everstone Level based upon Staked PURPLE --- \\
function levelCalc(staked = 0){
  staked = parseInt(staked);
  let levels = [1,2,3,4,8,12,16,32,64,999999];
  let rewards = [1,3,5,7,16,30,48,144,432];
  for (var i = 0; i < levels.length; i++) {
    if (staked < levels[i])
    {
      return (i);
      break;
    }
  }
}//END levelCalc

```
