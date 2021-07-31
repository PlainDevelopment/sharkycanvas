<div align="center">
    <h2>sharkycanvas</h2>
    <h4>Easily create Discord.js rank, welcome and goodbye images.</h4>
    <h5>npm i @plaindevelopment/sharkycanvas</h5>
    <p>This is not something that will not be updated. This was made for the bot "Sharky" and any issues are not for me to fix.</p>
</div>
<br>
### Dependancies
<br>
- fs
<br>
- canvas

### Examples
```js
const canvas = require("npm i @plaindevelopment/sharkycanvas"),
rankCardCanvas = new canvas.RankCard(),
welcomeCardCanvas = new canvas.Welcome(),
goodbyeCardCanvas = new canvas.Goodbye();

// Level/Rank Card
let image = await rankCardCanvas
    .setAvatar("url") // Avatar image URL
    .setXP("current", 0) // Current XP
    .setXP("needed", 100) // XP Needed To Level Up
    .setLevel(1) // Current Level
    .setRank(1) // Current Position (1st=1, 2nd=2)
    .setRankName("Default") // Special name for that level?
    .setUsername("Susan") // Username
    .setBackground("url") // Background image url
    
// Welcome Card
let image = await welcomeCardCanvas
  .setUsername("Susan") // Username
  .setDiscriminator(1234) // Users tag so Susan#1234 (1234)
  .setMemberCount(100) // Server member count
  .setGuildName("PD Server") // Server name
  .setAvatar("url") // Avatar image URL
  .setColor("border", "#8015EA") // Only mess with these if you know colour codes!
  .setColor("username-box", "#8015EA")
  .setColor("discriminator-box", "#8015EA")
  .setColor("message-box", "#8015EA")
  .setColor("title", "#8015EA")
  .setColor("avatar", "#8015EA")
  .setBackground("url") // Background image url

// Goodbye Card
let image = await goodbyeCardCanvas
  .setUsername("Susan") // Username
  .setDiscriminator(1234) // Users tag so Susan#1234 (1234)
  .setMemberCount(100) // Server member count
  .setGuildName("PD Server") // Server name
  .setAvatar("url") // Avatar image URL
  .setColor("border", "#8015EA") // Only mess with these if you know colour codes!
  .setColor("username-box", "#8015EA")
  .setColor("discriminator-box", "#8015EA")
  .setColor("message-box", "#8015EA")
  .setColor("title", "#8015EA")
  .setColor("avatar", "#8015EA")
  .setBackground("url") // Background image url
  
/*
To send any of these as a discord attachment:
After all options put
*/
.toAttachment();
const attachment = new Discord.MessageAttachment(image.toBuffer(), "welcome-image.png");
// Then just do
message.channel.send(attachment);
```
