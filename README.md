<div class="jhH5U r-iu80cxYriQzQ" data-rtid="iu80cxYriQzQ">
<div id="tw-ob" class="tw-src-ltr">
<div class="oSioSc">
<div id="tw-target">
<div id="kAz1tf" class="g9WsWb">
<div id="tw-target-text-container" class="tw-ta-container tw-nfl">
<blockquote>
<h3 style="text-align: center;"><em><strong><span style="color: #ff0000;">This plugin need an active bot with roles management to work.</span></strong></em></h3>
</blockquote>
&nbsp;
<p id="tw-target-text" class="tw-data-text tw-ta tw-text-small" dir="ltr" data-placeholder="Traduction"><span lang="en" tabindex="0">Discord has recently created a new Nitro Boost subscription system.</span></p>
<p dir="ltr" data-placeholder="Traduction">This plugin allows your user to link their steam and discord and ask for a reward for a boost.</p>

</div>
</div>
</div>
</div>
</div>
</div>
To create a discord bot, you have to go to <a href="https://discordapp.com/developers/">www.discordapp.com/developers</a>

Once you have created your bot, you have to invite him to your server you just have to get him a Token and put it in the config file.
<div></div>
<div></div>
<h3><span style="text-decoration: underline;"><strong>How to install:</strong></span></h3>
<div>-The bot requires NodeJS to work =&gt; <a href="https://nodejs.org/en/download/">https://nodejs.org/en/download/</a></div>
<div>-You have to start a CMDDOS from the bot folder and tip the command:</div>
<blockquote>
<div style="padding-left: 30px;">-npm install discord.io</div>
<div style="padding-left: 30px;">-npm install discord.js</div>
<div style="padding-left: 30px;">-npm install body-parser</div>
<div style="padding-left: 30px;">-npm install express</div>
<div style="padding-left: 30px;">-npm install mysql</div></blockquote>
<div>-Configure auth.json</div>
<blockquote>
<div>You have to fill up "token" from the <a href="https://discordapp.com/developers/applications/" target="_blank" rel="noopener noreferrer">discord application website</a></div>
<div>You have to setup your MySQL database information (follow this guide if you don't have mysql <a href="https://dev.mysql.com/doc/workbench/en/wb-installing-windows.html" target="_blank" rel="noopener noreferrer">Mysql Guide</a>)</div></blockquote>
<h3 dir="ltr" data-placeholder="Traduction"><span style="text-decoration: underline;"><strong>Commands:</strong></span></h3>
<blockquote>
<p dir="ltr" data-placeholder="Traduction">/auth (allow you to link your steam to your discord)</p>
<p dir="ltr" data-placeholder="Traduction">/boosted (reward yourself if you have boosted the discord server)</p>
</blockquote>
<h3></h3>
<h3 class="dURPtb"><span style="text-decoration: underline;"><strong>Bot PM command:</strong></span></h3>
<blockquote>!auth Your_Code</blockquote>
<h3 class="dURPtb"><span style="text-decoration: underline;"><strong>Default config:</strong></span></h3>

```json
{
  "Permission": [],
  "Settings": {
    "Bot Token": "",
    "Chat Prefix": "<color=#1874CD>(Auth)</color>",
    "Chat Icon (SteamID64)": 0,
    "IP Address": "127.0.0.1",
    "Port": 3306,
    "UserName": "root",
    "Password": "",
    "Database Name": "rustdb"
  },
  "Authentication Code": {
    "Code Lifetime (minutes)": 60,
    "Code Length": 5,
    "Lowercase": false
  }
}
```

<h3 class="iVZmYYi_Hw7Q-pvVKlfEP0Yk"><span style="text-decoration: underline;"><strong>Default Lang file:</strong></span></h3>

```json
{
  "Code Generation": "Here is your code: <color=#1874CD>{0}</color>\n\n<color=#EE3B3B>What's next:</color>\n<color=#1874CD>1</color> - Join the Discord at \n<color=#1874CD>2</color> - PM your code to the bot called 'XXX'\n\nHere is the discord invite link - <color=#1874CD></color>",
  "Code Expired": "Your code has <color=#EE3B3B>Expired!</color>",
  "Authenticated": "Thank you for authenticating your account!",
  "NotRegistered": "You may register your discord account first !",
  "Already Authenticated": "You have already <color=#1874CD>authenticated</color> your account, no need to do it again!",
  "Unable to find code": "Sorry, we couldn't find your code, please try to authenticate again, If you haven't generated a code, please type /auth in-game",
  "BotKeyNotSet": "The bot token has not been set, please ask an admin.",
  "PermissionSet": "You have been granted with perm <color=#EE3B3B>{0}</color>.",
  "PermissionNotSet": "The permissions list is empty, please ask an admin."
}
```
<h3><span style="text-decoration: underline;"><strong>SQL Infos:</strong></span></h3>

```sql

CREATE TABLE leavedclient (
 discordid varchar(255) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1;
CREATE TABLE stats_player_discord (
 id bigint(20) NOT NULL,
 steamid varchar(50) NOT NULL,
 discordid varchar(50) NOT NULL,
 confirmed tinyint(1) DEFAULT '0',
 code varchar(10) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1;
ALTER TABLE leavedclient
 ADD PRIMARY KEY (discordid);
ALTER TABLE stats_player_discord
 ADD PRIMARY KEY (id),
 ADD UNIQUE KEY steamid (steamid),
 ADD UNIQUE KEY discordid (discordid);
ALTER TABLE stats_player_discord
 MODIFY id bigint(20) NOT NULL AUTO_INCREMENT;

```
<a style="font-size: 0.9rem;" href="https://support.discordapp.com/hc/fr/articles/360028038352-Server-Boosting-" target="_blank" rel="noopener noreferrer">More details here</a>
