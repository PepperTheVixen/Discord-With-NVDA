# Using Discord on Windows with NVDA

## Introduction
Discord is a multiplatform chat client. This guide will specifically cover the use of the Discord desktop client on Windows with the NVDA screen reader.
## Useful Resources
- [NVDA screen reader](https://www.nvaccess.org/)
- [NVDA user guide](https://www.nvaccess.org/files/nvda/documentation/userGuide.html?)
- [Discord app](https://discord.com/)
- [Discord hotkeys](https://support.discord.com/hc/en-us/articles/225977308--Windows-Discord-Hotkeys)
## Prerequisites
- You are running Windows 10 or 11
- You are running NVDA and know how to use it
- You have downloaded and installed [Discord For Windows](https://discord.com/api/downloads/distributions/app/installers/latest?channel=stable&platform=win&arch=x86)
## Note for non-NVDA users
If you are using a different screen reader, such as JAWS or Dolphin, interface navigation will be largely the same since Discord is a web app, however you will need to use the navigation style specific to your screen reader. This includes the equivalents to web-element navigation and browse/focus mode for interacting with tree views and text fields.

## Getting Started
Once you launch Discord, you'll be presented with a login screen. If you do not have an account, you can create one here. There are no major accessibility hurdles here, and NVDA functions as expected.
After signing up, you can begin to use Discord.
## Interface
Discord is built in Electron and functions like a website. This means you can use web navigation throughout the desktop client.
The interface is divided into 6 distinct sections: server sidebar, user/channel list, user area, the channel header, channel area, and the members list. All of these sections can be reached via landmark navigation, however not all of them may be present at once, depending on the active context.
### Server Sidebar
This is the first landmark available. It is a tree view which contains all of the servers you are currently a member of. To navigate this sidebar, activate focus mode and move up and down. NVDA may start focused at the bottom. To resolve this, press home while in focus mode to move to the "direct messages" at the top of the list. You will find options to create a server or browse public servers at the bottom of the list.
You can open the context menu for various server options by moving to the desired server in the list and pressing the applications key or shift+f10. To select a server, move to the desired server and press enter. You may then exit focus mode.
### Private Channels/Server Channels
This is the second landmark available in the client. It is context-sensitive to the option you selected in the server sidebar and will either display your private messages or the channels you have viewing permissions for in a selected server.
#### Private Channels
If you have selected "direct messages" in the server sidebar, you will see a list of actie private conversations in this region. When you first move to this landmark, NVDA will be focused on "button start or find a private conversation". This button will open the quick switcher which will be explained later.
Below this button, NVDA will announce a list which begins with two links. "Friends" will open a view of all your friends. This region is not a landmark and will be discussed later. The next item is a link labelled "Nitro". This will open information about Discord Nitro. This content is not a landmark. If you wish to read it, navigate to the next level 3 heading within Discord after activating the link, otherwise you can safely ignore it.
Afterward, you will find a level 2 heading, "Direct Messages" immediately followed by a "create DM" button. This button opens a menu that allows you to make a new private channel with up to 9 participants. It will be discussed later. Below this button, the list will continue if you have any private channels. You can navigate these either by link or list item. They will read "<username>, direct message, link". Press enter on the desired username to open its corresponding private channel.
#### Server Channels
If you have selected a server in the server sidebar, you will instead see a list of all the channels in the selected server that you have access to. This area can be most easily navigated with button, list item, and link navigation.
The name of this landmark is dependent on the name of the server. The first element encountered is an unlabeled button. This button is for server-boosting whic requires a Nitro subscription. If you activate it, you will be put into another region telling you the benefits of Nitro. You can close this content by pressing escape, however it will place you in the members list landmark. Move back to the server channels landmark.
Next in the area is a level 1 heading with the server name followed by a collapsed button that lets you perform various server actions. Many of these are the same as the actions you can perform in the context menu in the server sidebar. These options may change depending on your server permissions. Below this is yet another button for buying server boosts. This one, however, is labeled. NVDA also likely announced a list with several items. This button is not part of the list.
Below this, you will encounter categories, text channels, and voice channels. These channels can vary wildly from server to server. The names may include text, emojis, or both. Categories and voice channels with no users are buttons. Text channels and voice channels with users present are links. All of these are items in the channels list.
A voice channel with users present will appear as a link, rather than a btton, and will display the names of the users currently in the channel below it. These users will appear as buttons. Each name may include a word such as "live", "muted", or "deafened" appended to their name. These signify that they are either streaming video to that channel, muted and unable to speak, or deafened and unable to hear or sspeak. These options can be controlled locally by the user or by a user with adminstrative permissions.
A text channel with messages that you have not read will include "unread" appended to its name. A text channel in which another user has mentioned you or a server group you are in will have a number corresponding to the number of unread mentions appended to its name. Categories can be collapsed or expanded to make navigation through the list easier.
### User Area
This landmark contains controls for your status, microphone, and speakers. The first element is a collapsed button "set status". This will open a new region and move focus to it automatically.