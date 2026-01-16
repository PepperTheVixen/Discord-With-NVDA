# Using Discord on Windows with NVDA

**NOTICE:** This guide was last updated on`2026-01-15`.

## Introduction

Discord is a multiplatform chat client built in Electron and navigated with web navigation commands. This guide is written specifically for the Discord desktop client on Windows, however the knowledge can apply to the Discord desktop clients on other operating systems as well as Discord on the web.
This guide will attempt to be as comprehensive as possible when describing the desktop client interface so that a blind screen reader user from a broad range of skill levels may benefit from the information.
The purpose of this guide is not to teach you how to use NVDA or any other screen reader, however NVDA-specific instructions will be provided when necessary, such as for working around interface quirks and bypassing usability pitfalls.

## License

Copyright (C)  2016  Jenna Pepper (@PepperTheVixen).
Permission is granted to copy, distribute and/or modify this document
under the terms of the GNU Free Documentation License, Version 1.3
or any later version published by the Free Software Foundation;
with no Invariant Sections, no Front-Cover Texts, and no Back-Cover Texts.
A copy of the license is included in the project file entitled "[license](./license)".

### Corrections, Contributions, & Suggestions

These docs are currently maintained by a single volunteer. They try their best, but they will probably make a few mistakes or forget a feature here and there.
If you've spotted a mistake, typo, or inaccuracy, please feel free to report it by submitting an [issue](https://github.com/PepperTheVixen/Discord-With-NVDA/issues).

Want to contribute to the docs? Maybe add instructions for other screen readers or mention quirks specific to the web app? Submit a [pull request](https://github.com/PepperTheVixen/Discord-With-NVDA/pulls)!

### Prerequisites & Assumptions

- You are running Windows 10 or 11
- You are running NVDA and know how to use it
- You have downloaded, installed, and launched Discord for Windows

### Guide Terminology

- Landmark: an accessibility landmark present within the Discord interface.
- State: referring to the status of the app as a whole or parts of the app such as, focused server, focused channel, voice channel, microphone status, etc.
- Persistent: describing an interface element that will not change its title and will not change its values significantly regardless on current application state.
- Dynamic: describing an interface element  that may change its title or values significantly based on current application state.
- Fixed: describing a major section of the interface that will not move or disappear.
- Ephemeral: describing a major section of the interface which may move or disappear completely.

## Useful Resources

- [NVDA screen reader](https://www.nvaccess.org/)
- [NVDA user guide](https://www.nvaccess.org/files/nvda/documentation/userGuide.html?)
- [NVDA on GitHub](https://github.com/nvaccess/nvda)
- [Discord app](https://discord.com/)
- [Discord hotkeys list](https://support.discord.com/hc/en-us/articles/225977308--Windows-Discord-Hotkeys)
- [Discord Accessibility Resources](https://discord.com/accessibility)

## Login Interface

The login screen includes a a series of labeled edit fields and buttons for the most important elements.

- email or phone number: edit field
- password: secure edit field
- forgot your password: button
- log in: button
- register: button
- log in with QR code: level 2 heading
- or sign in with passkey: button

## Main Interface

The main interface is divided into 6 distinct sections. All of these sections can be reached via landmark navigation, however not all of them may be present at once.
Despite the fact that the landmarks being described will change name, and change role in some narrow cases, it's helpful to imagine 6 distinct sections and form spatial relationships between them.
Visually, Discord is organized into 3 or 4 columns that span the width of the app. The columns are of varying widths and leave the most space for the main content area down the center of the app. From left to right, they are: servers sidebar, user/channel list, channel area, and members list.
There are 3 exceptions to the column layout: the user area takes up a small portion of the user/channel list column at the bottom, the channel header occupies the uppermost portion of the channel area, and the member list will display multiple landmarks when viewing a profile.

Quickly jump to a specific interface section.

- [servers sidebar](#servers-sidebar)
- [user/channel list](#channel-list)
- [user area](#user-area)
- [channel header](#channel-header)
- [channel area](#channel-area)
- [members list](#members-list)

### Servers Sidebar

Persistent, Fixed: contents will not change often, and the landmark will not disappear from the main interface.

This landmark is the first you will encounter in the client. It is a tree view that allows you to switch between servers and direct messages. Starting from the top of the tree view, you will find:

- Direct Messages (level 1, persistent)
  - Shows all direct messages in the channel list
  - see [Private Channels](#private-channels) for more info
- Direct messages grouping (level 2, dynamic, ephemeral)
  - appears for messages that you haven't read
  - changes often based on incoming messages
- Servers Grouping (level 1, persistent)
  - displays all servers you are part of
  - will change in length as you join and leave servers
  - see [Server Channels](#server-channels) for more info
- Add a Server (level 1, persistent)
  - opens a modal that allows you to create your own server
- Discover (level 1, persistent)
  - shows options for discovering servers, apps, and other Discord features in the channel list
  - see [Discover](#discover) for more info

### Channel List

Dynamic, Fixed: The title of this landmark and its contents will change frequently based on app state, but the landmark will not disappear from the main interface.

This is the second landmark in the client. When viewing direct messages, it will be titled "direct messages". When viewing a server, the landmark will bear the same name as the server title.

#### Private Channels

Private channels (direct messages) will be displayed here if you have selected "Direct Messages in the [servers sidebar](#servers-sidebar).

You will encounter a button labeled "Find or start a conversation" which opens the quick switcher.
Following this is a list that can be navigated in browse or focus mode that will display pending friend requests and conversation requests (if any) as well as all of your direct messages and groups. The context menu is available for all chats in this list.

#### Server Channels

All the categories and channels available to you in a specific server will be displayed here after selecting a server from the [servers sidebar](#servers-sidebar).
You will first encounter 2 buttons:

1. Server Actions. This opens a menu for making changes to the current server. Options can be navigated in focus mode and will changed based on your server permissions
2. Invite to Server. This button appears as unlabeled to NVDA. It will open a modal that may allow you to invite other people to the current server depending on your permissions

After these buttons, you will encounter a level 2 heading labeled "Channels". Below this heading is a list holding all server channels and categories.

The list of channels can be navigated in browse mode or focus mode. This list is highly dynamic and you should expect each server to organize its contents differently. Many servers also reorganize and rename channels from time to time, so it's important to be familiar with the underlying navigation patterns rather than memorizing one specific server channel layout.
The first two items in the list, "events" and "browse channels", will show server events and allow you to customize which channels are shown, respectively.

This table gives an overview of each channel type.

| Name | type | purpose | Important Notes |
| --- | --- | --- | --- |
| category | button | divides channels into organizational units | collapsing does not work properly with NVDA |
| text channel | link | a typical channel with text communication | most common channel type |
| voice channel | button | a voice chat | When connected, appears as link, displays connected users as buttons in channel list |
| thread | button | a text chat that has branched off of a text channel | appears directly below associated channel |
| forum | link | a channel with many separate threads | hard to distinguish from text channels |

##### Categories

To keep servers organized, owners can group all of their channels into common categories; some may organize by channel type while others organize by channel purpose. It is common to encounter a mixture of both.
Categories appear to NVDA as buttons. This makes it very easy to browse channel categories on a well-organized server and only move through individual channels when you find the desired category.
While categories are collapsible, the effect only functions with NVDA some of the time.
Within a category, you will encounter a mixture of text channels, threads, forum channels, and voice channels. The first 3 channel types appear as links, and voice channels appear as buttons.

##### Text Channels

Text channels are by far the most common type of channel in Discord. When selected, they will display the channel info and contents in the [channel header](#channel-header) and the [channel area](#channel-area).
These channels present text and other media as linear conversations like other chat apps.
Text channels with unread messages will have "(unread)" appended to their name in the channel list. If a user mentions you in a text channel, a count will be appended to the channel name. This number corresponds to the amount of times you have been mentioned in that channel.
Check the section on [navigating text channels](#navigating-text-channels) for more info.

##### Voice Channels

When you join a voice channel, it will appear as a button instead of a link in the channels list. The users in the voice channel will be added to the list and appear as buttons for as long as you remain connected.
When these users are displayed in the channels list, their names will include extra words and buttons based on activity, server badge, and microphone state.
While you are focused on a voice channel, regardless of connection state, the channel header and channel area will disappear from the main interface.
Check the section on [navigating voice channels](#navigating-voice-channels) for more info.

##### Threads

A thread is a self-contained conversation that can be found in text channels and forum channels.
Threads that are part of text channels may show up as buttons directly after the channel link and will show the conversation info and contents in the [channel header](#channel-header) and the [channel area](#channel-area) when selected.
Check the section on [navigating threads and forums](#navigating-forums--threads) for more info.

##### Forums

Forums are indistinguishable from text channels unless they are explicitly identified as forums in their channel name. Currently, even the [channel header](#channel-header) identifies a forum as a text channel.
When selected, the [channel area](#channel-area) is temporarily replaced by a view of all threads within the forum.
Check the section on [navigating threads and forums](#navigating-forums--threads) for more info.

#### Discover

<!-- todo: discover -->

### User Area

Persistent, Fixed: Contents will not update dramatically, and frequent value updates only occur in some app states. This landmark will not disappear from the main interface.

This landmark provides information about your active user account, connected voice channel, and toggles for frequently-used settings.

- Set Status
  - opens a dialogue for configuring your current activity status
  - see [Set Status Menu](#set-status-menu) for more info
- mute switch
  - toggles whether or not your selected audio input device can be heard in a voice chat
- input options
  - opens a menu to select and configure the active microphone
  - see [input options](#input-options-menu) for more info
- deafen switch
  - toggles whether or not you can hear a voice chat through your selected audio output device
- output options
  - opens a menu to select and configure the active listening device
  - see [output options](#output-options-menu) for more info
- User Settings
  - appears as an unlabeled button with its label directly following it
  - opens the user settings dialogue
  - see [user settings](#user-settings-dialogue) for more info

#### When Connected to Voice

When you are connected to a voice channel, the user area will display additional relevant content and options at the top of the landmark:

- a button displaying your current ping
  - may appear unlabeled if no ping is being reported
  - will announce ping as a number (example: "12 ms")
  - toggles additional details about your connection to the voice channel at the bottom of the main interface (synced with voice details toggle)
- voice details button
  - may have an additional label such as "Voice Details Voice Connected"
  - toggles additional details about your connection to the voice channel at the bottom of the main interface (synced with ping button)
- noise suppression control
  - may appear unlabeled with its label immediately following it in some app states
  - opens a menu that allows you to toggle Discord's built-in noise suppression
    - the menu is located at the bottom of the main interface
    - pressing escape closes the menu but does not return focus to the user area
    - navigate by previous landmarks to return to the the user area
- disconnect button
  - may appear unlabeled with its label immediately following it in some app states
  - immediately disconnects you from the current voice channel
- camera button
  - may appear unlabeled with its label immediately following it in some app states
  - toggles your selected webcam on or off
  - while the button is marked as collapsed, there doesn't appear a to be a way to expand it
- screen-share button
  - may appear unlabeled with its label immediately following it in some app states
  - opens the screen-sharing dialogue
  - see the [share your screen dialogue](#share-your-screen-dialogue) for more info
- activities button
  - may appear unlabeled with its label immediately following it in some app states
  <!-- todo: add more brief notes -->
  - see the [activities dialogue](#activities-dialogue) for more info
- soundboard button
  - may appear unlabeled with its label immediately following it in some app states
  - opens the soundboard dialogue for playing soundbites in in the connected voice channel
  - see the [soundboard dialogue](#soundboard-dialogue) for more info

### Channel Header

Dynamic, Fixed: Contents will update frequently based on app state, but the landmark will not disappear from the main interface.

The channel header provides information about the focused channel. For text channels, this includes the channel name, description, notification and member display settings, and a search input field.
<!-- todo: expand this section -->

### Channel Area

Dynamic, Ephemeral: expect the content title and content to change frequently as app state changes and messages are posted and edited in channels. This landmark may also disappear under specific app states, such as when viewing a [forum](#forums).

This area contains the main content of the focused channel: messages in a text channel, threads in a forum, and connected users in a voice channel.

- [navigating text channels](#navigating-text-channels)
- [navigating voice channels](#navigating-voice-channels)
- [navigating forums and threads](#navigating-forums--threads)

### Members List

Dynamic, Ephemeral: Expect the information here to update frequently and significantly based on app state and user activity. This landmark can be hidden manually.

When focused on a server, this landmark will show all members who have access to the focused channel.
It can be hidden and unhidden manually using `ctrl + u`.
Users can be navigated as a list, however users may be arranged differently based on server configuration. A server may divide users into several ranks or only use one or two. Each rank is represented by a level 3 heading in the users list.

#### When Viewing a Direct Message

If the landmark is on screen, it will instead become a series of landmarks displaying the profile of the user you are having a conversation with.

- User's Profile
  - displays the user's profile, including, name, avatar, status, common servers, and more
- Current Activity
  - displays what the user is currently doing, such as which voice channel they are in
  - may offer the ability to join them if you have the correct permissions
  - may show multiple names if they are in an activity with multiple users
- About me (2 Landmarks)
  - "About Me " h4 in one region immediately followed by a "About Me" h4 in the next land,ark
  - displays the user's description
-Member Since
  - shows when the user first joined Discord

There are some items which are part of the profile but are positioned after the final landmark.

- Mutual Servers
  - shows which servers you and the user are both in
  - is presented as a list, but cannot be navigated via list item with NVDA
  - can be navigated via buttons
- Mutual Friends
  - shows other users that are both friends of you and the focused user
  - is presented as a list, but cannot be navigated via list item with NVDA
  - can be navigated via buttons
- View Full Profile

## Navigating within channels

Each channel type will require different navigation strategies. Below are sections on the major channel types

### Navigating Text Channels

<!-- todo: navigating text channels -->

### Navigating Voice Channels

<!-- todo: navigating voice channels -->

### Navigating Forums & Threads

<!-- todo: forums and threads -->

## Other Major Interface Elements

Below are a collection of interface elements that are not part of the main interface but are still import to understand.

### Activities Dialogue

<!-- todo: activities -->

### Input Options Menu

<!-- todo: input options menu -->

### Output Options Menu

<!-- todo: output options menu -->

### Share Your Screen Dialogue

<!-- todo: share your screen dialogue -->

### Soundboard Dialogue

<!-- todo: soundboard -->

### Set Status Menu

Context: [user area](#user-area)

After opening this menu, your focus will move to a new area which contains options for setting your active account's activity status. The options will be split into two lists for easier navigation.

The first series of options contain shortcuts to your profile as well as custom status options:

- profile graphic button
  It will use your username and current status as its name
  - opens your Discord profile in a new dialogue
- custom status button
  - opens a dialogue to set custom text as your activity status
- another profile button
  - opens your full profile
- your display name
- "copy username" button
  - copies your username (and not your display name)
- yet another profile button
  - takes you to your full profile
- profile information...
  - these are several elements including your username, pronouns, and the "about me" section

The next series of elements allow you to edit your profile, set your status, and switch accounts

- edit profile button
  - opens a dialogue to edit your profile info
- "Your Status" button
  - opens a menu for choosing preset activity statuses
    - navigating this submenu is easiest in focus mode
- "switchSwitch Accounts" button
  - opens a dialogue that allows you to switch between multiple accounts, if you have more than one, and add a new account to switch between
- "More Info" button
  - appears to open the same dialogue as above

### User Settings Dialogue

<!-- todo: user settings -->
