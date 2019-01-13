# StreamDeck-Discord

StreamDeck-Discord is a C++ plugin for the Elgato StreamDeck for controlling self-mute and self-deafen in the Discord app.

# Installation

Installation and demo video: https://youtu.be/MSMbRtj2fFA

1. Download the `com.fredemmott.discord.streamDeckPlugin` file from [the releases page](https://github.com/fredemmott/StreamDeck-Discord/releases/latest), and double-click it.
1. Add a mute or deafen button to your streamdeck
1. Go to [the Discord developer portal](https://discordapp.com/developers), and create an application
1. Go to 'OAuth2' on the left hand side
1. Add `https://localhost/` as a redirect URI
1. go back to 'General Information'
1. copy the client ID and paste it into 'app ID' in the StreamDeck button properties
1. copy the client secret and paste it into 'app secret' in the StreamDeck button properties
1. Discord should now ask you for permission a few times, then you're done :)
1. You might get a firewall prompt. You need to allow it.

# Limitations

- only one application can control Discord voice settings at a time. Stop anything else that controls Discord mute/deafen, such as the Discord applet in Logitech Gaming Software
- mute/deafen only apply while the application is running. For example, if you mute the microphone, then quit the StreamDeck software, the microphone is no longer muted.

These limitations are imposed by Discord and can not be fixed by this plugin.

# Firewall?

Discord plugins use OAuth2. The flow is basically:

1. this plugin asks the local Discord app for a code
1. the Discord app gives this plugin a code
1. the plugin asks the Discord web API to convert the code into an OAuth token
1. the Discord API gives the plugin the token
1. the plugin uses the token to log in to the client

The third step requires internet access.

# License

This project is [MIT-licensed](LICENSE).
