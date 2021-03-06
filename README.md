## Jackett

[![GitHub issues](https://img.shields.io/github/issues/Jackett/Jackett.svg?maxAge=60&style=flat-square)](https://github.com/Jackett/Jackett/issues)
[![GitHub pull requests](https://img.shields.io/github/issues-pr/Jackett/Jackett.svg?maxAge=60&style=flat-square)](https://github.com/Jackett/Jackett/pulls)
[![Github Releases](https://img.shields.io/github/downloads/Jackett/Jackett/total.svg?maxAge=60&style=flat-square)](https://github.com/Jackett/Jackett/releases/latest)
[![Docker Pulls](https://img.shields.io/docker/pulls/linuxserver/jackett.svg?maxAge=60&style=flat-square)](https://hub.docker.com/r/linuxserver/jackett/)

This project is a new fork and is recruiting development help.  If you are able to help out please contact us.

Jackett works as a proxy server: it translates queries from apps ([Sonarr](https://github.com/Sonarr/Sonarr), [Radarr](https://github.com/Radarr/Radarr), [SickRage](https://sickrage.github.io/), [CouchPotato](https://couchpota.to/), [Mylar](https://github.com/evilhero/mylar), etc) into tracker-site-specific http queries, parses the html response, then sends results back to the requesting software. This allows for getting recent uploads (like RSS) and performing searches. Jackett is a single repository of maintained indexer scraping & translation logic - removing the burden from other apps.

Developer note: The software implements the [Torznab](https://github.com/Sonarr/Sonarr/wiki/Implementing-a-Torznab-indexer) (with [nZEDb](https://github.com/nZEDb/nZEDb/blob/dev/docs/newznab_api_specification.txt) category numbering) and [TorrentPotato](https://github.com/RuudBurger/CouchPotatoServer/wiki/Couchpotato-torrent-provider) APIs.



#### Supported Systems
* Windows using .NET 4.5
* Linux and OSX using Mono 4 (With v3 you'll experience crashes).


#### Supported Private Trackers
 * 7tor
 * Abnormal
 * AlphaRatio
 * AlphaReign
 * Andraste
 * AnimeBytes
 * AnimeTorrents
 * AOX
 * Apollo (XANAX)
 * Avistaz
 * BakaBT
 * bB
 * Best Friends
 * BeyondHD
 * Bit-City Reloaded
 * BIT-HDTV
 * BitHQ
 * BitHUmen
 * BitMeTV
 * BitSoup
 * Bitspyder
 * Blu-bits
 * BlueBird
 * BTN
 * CHDBits
 * CinemaZ
 * DanishBits
 * DataScene
 * Demonoid
 * DigitalHive
 * Dream Team
 * EoT-Forum
 * eStone
 * Ethor.net (Thor's Land)
 * FANO.IN
 * FileList
 * Freedom-HD
 * Freshon
 * FunFile
 * FunkyTorrents
 * Fuzer
 * Ghost City
 * GODS
 * Gormogon
 * Hardbay
 * HD4Free
 * HD-Space
 * HD-Torrents
 * HDClub
 * HDSky
 * Hebits
 * Hon3y HD
 * Hounddawgs
 * House-of-Torrents
 * Hyperay
 * ICE Torrent
 * ILoveTorrents
 * Immortalseed
 * Infinity-T
 * IPTorrents
 * LinkoManija
 * M-Team - TP
 * Magico
 * Mononoké-BT
 * MoreThanTV
 * MyAnonamouse
 * myAmity
 * MySpleen
 * Nachtwerk
 * NCore
 * NetHD
 * New Real World
 * NextGen
 * Norbits
 * nostream
 * notwhat.cd
 * PassTheHeadphones
 * PassThePopcorn
 * PirateTheNet
 * Pretome
 * PrivateHD
 * QcTorrent
 * RapideTracker
 * RevolutionTT
 * Rockhard Lossless
 * RuTracker
 * SceneAccess
 * SceneFZ
 * SceneTime
 * SDBits
 * Secret Cinema
 * Shareisland
 * ShareSpaceDB
 * Shazbat
 * Shellife
 * SpeedCD
 * Superbits
 * The Horror Charnel
 * The New Retro
 * The Shinning
 * TehConnection
 * TenYardTracker
 * Torrent Network
 * Torrent Sector Crew
 * TorrentBD
 * TorrentBytes
 * TorrentDay
 * TorrentHeaven
 * Torrenting
 * TorrentLeech
 * Torrents.Md
 * TorrentShack
 * Torrent-Syndikat
 * ToTheGlory
 * TranceTraffic
 * TransmitheNet
 * TV Chaos UK
 * TV-Vault
 * u-Torrent
 * UHDBits
 * World-In-HD
 * WorldOfP2P
 * x264
 * XSpeeds
 * Xthor
 * Xtreme Zone

#### Installation on Windows

We recommend you install Jackett as a Windows service using the supplied installer. You may also download the zipped version if you would like to configure everything manually.

To get started with using the installer for Jackett, follow the steps below:

1. Download the latest version of the Windows installer, "Jackett.Installer.Windows.exe" from the [releases](https://github.com/Jackett/Jackett/releases/latest) page.
2. When prompted if you would like this app to make changes to your computer, select "yes".
3. If you would like to install Jackett as a Windows Service, make sure the "Install as Windows Service" checkbox is filled.
4. Once the installation has finished, check the "Launch Jackett" box to get started.
5. Navigate your web browser to: http://127.0.0.1:9117
6. You're now ready to begin adding your trackers and using Jackett.

When installed as a service the tray icon acts as a way to open/start/stop Jackett. If you opted to not install it as a service then Jackett will run its web server from the tray tool.

Jackett can also be run from the command line if you would like to see log messages (Ensure the server isn't already running from the tray/service). This can be done by using "JackettConsole.exe" (for Command Prompt), found in the Jackett data folder: "%ProgramData%\Jackett". 

#### Installation on Linux/OSX
 1. Install [Mono 4](http://www.mono-project.com/download/) or better
       * Follow the instructions on the mono website and install the `mono-devel` package.
       * On Red Hat/CentOS  the `mono-locale-extras` package is also required
 2. Install  libcurl:
       * Debian/Ubunutu: `apt-get install libcurl-dev`
       * Redhat/Fedora: `yum install libcurl-devel`
       * For other distros see the  [Curl docs](http://curl.haxx.se/dlwiz/?type=devel).
 3. Download and extract the latest `Jackett.Binaries.Mono.tar.gz` release from the [releases page](https://github.com/Jackett/Jackett/releases) and run Jackett using mono with the command `mono JackettConsole.exe`.

Detailed instructions for [Ubuntu 14.x](http://www.htpcguides.com/install-jackett-on-ubuntu-14-x-for-custom-torrents-in-sonarr/) and [Ubuntu 15.x](http://www.htpcguides.com/install-jackett-ubuntu-15-x-for-custom-torrents-in-sonarr/)

#### Installation using Docker
Detailed instructions are available at [LinuxServer.io Jackett Docker](https://hub.docker.com/r/linuxserver/jackett/). The Jackett Docker is highly recommended, especially if you are having Mono stability issues or having issues running Mono on your system eg. QNAP, Synology. Thanks to [LinuxServer.io](https://linuxserver.io)

#### Installation on Synology
Jackett is available as beta package from [SynoCommuniy](https://synocommunity.com/)

#### Troubleshooting

* Command line switches

You can pass various options when running via the command line, see --help for details.

* Unable to  connect to certain trackers on Linux

Try running with the "--SSLFix true" if you are on Redhat/Fedora/NNS based libcurl.  If the tracker is currently configured try removing it and adding it again. Alternatively try running with a different client via --UseClient (Warning: safecurl just executes curl and your details may be seen from the process list). You can also try running with the "--IgnoreSslErrors true" option which is useful if the site has an invalid SSL certificate.

*  Enable logging

You can get additional logging with the switches "-t -l".  Please post logs if you are unable to resolve your issue with these switches ensuring to remove your username/password/cookies.

#### Creating an issue
Please supply as much information about the problem you are experiencing as possible. Your issue has a much greater chance of being resolved if logs are supplied so that we can see what is going on. Creating an issue with '### isn't working' doesn't help anyone to fix the problem.

### Contributing
All contributions are welcome just send a pull request.  Jackett's framework allows our team (and any other volunteering dev) to implement new trackers in an hour or two. If you'd like support for a new tracker but are not a developer then feel free to leave a request on the [issues page](https://github.com/Jackett/Jackett/issues).  It is recommended to use Visual studio 2015 when making code changes in this project.  We currently only support private trackers.


### Screenshots

![screenshot](https://i.imgur.com/0d1nl7g.png "screenshot")
