# 19625_Slack.hsl
Gira Homeserver to Slack Webhook Logic module

Ever wanted to receive notifications from your Gira Homeserver in Slack? Look no further! This logic module does just that. 

The possibilities are endless. Get notified if your front door opens, or if an alarm is triggered, or if the temperature in your house is to low. You name it, you've got it!

Installation
------------
Just copy 19625_Slack_Vx.xx.hsl to the logic folder of your HomeServer and (re)start HomeServer Experte. You'll find the module in the folder Smarterliving. 

Usage
-----
Create two new HS Internal _14-Byte text_ Objects: 
  - Slack Message 
  - Slack Status 

Using the Graphic Logic Editor, create a new worksheet and add the Smarterliving\Slack logic element to the worksheet. 

#### Input 1 - Slack Webhook URL
Copy/Paste your Slack Webhook URL in this field. This URL looks like: 
``` https://hooks.slack.com/services/T025XXXX/B0XXXXXXXX/tKJxxxxxxxxxxx ```

#### Input 2 - Message
Connect this input with the HS Internal Communication Object ```Slack Message``` that you've created earlier

#### Input 3 - Channel
_Optional:_ Incoming Slack webhooks have a default channel, but it can be overridden using this input.  

#### Input 4 - Username 
_Optional:_ While 19625_Slack defaults to ```Gira HomeServer```, you can use this input to override this setting and assign another name to your Slackbot. 

#### Input 5 - Icon_Emoji
_Optional:_ You can customize the icon of your Incoming Webhook using one of the Slack Icons, like ```:ghost:```.

#### Input 6 - Icon_URL
_Optional:_ 19625_Slack defaults to a Gira Logo file, currently stored at [Amazon](https://s3.eu-central-1.amazonaws.com/gira.homeserver/gira_icon175x175-1.png). Should you wish to use your own Icon, upload your graphic file to a publicly accessible website and enter it's URL in this input field. 

#### Output 1 - Status
Currently 19625_Slack does not output a status, but at least one output is required by the HomeServer. Connect this output to the HS Internal Communication Object ```Slack Status``` that you've created earlier. 

You are now ready to start using 19625_Slack! Using any of the supported means to set a value to a Communication Object will send your message to Slack right away. 

Files Included
--------------
- 19625_Slack_Vx.xx.hsl - HomeServer Logic file. Copy this to your logic folder. 
- 19625_Slack.py - Source in Python
- log19625.html - Helpfile. Copy this to html\de or html\en 
- LICENSE - GNU v3 Public License 
- LogikGen.py - KNX-User-Forum Logik Tester, very useful tool if you want to debug logic modules. Used by test.sh
- test.sh - simple script that compiles the source and starts LogikGen for debugging. 
- README.md - this file 

Support
-------
Non whatsoever. Feel free to raise an issue on Github though and/or ask for help at [KNX-User-Forum](http://knx-user-forum.de). 

The module was tested and runs succesfully on a HomeServer 4 with Experte 4.4 (4.4.0.151203R)

Credits
-------
Credits where credits are due! 

Out of the box a Gira HomeServer can do many things, however connecting to Slack, which requires the use of well established standards like HTTPS, POST and JSON is a step to far for a Gira HomeServer.

Luckily some fine folks at the German [KNX User Forum](http://knx-user-forum.de) have found a way to extend the HomeServer logic modules, which are written in a subset of the Python language, enabling developers to use almost all of the full power of the Python language and it's built-in modules like json, urllib2 etc. 

This logic module would not be possible without their efforts.

Roadmap
-------
Oh man, wouldn't it be nice if you could also send commands back to your HomeServer using Slack?

While I'm very positive that this is possible, my limited knowledge of Python and time constraints currently prevent me from pursuing this feature in the near future. 

However, as this is open source and this module is available on [Github](https://github.com/ottonet/19625_Slack) feel free to issue a PR if you have the time and knowledge to add this feature! 
