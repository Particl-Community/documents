'!tag download'

**File verification**

*Being your own bank with cryptocurrency related products brings some responsibilities to you. One of them is to take security serious. Please do verify that the file you downloaded is untainted in any way. We show you how to verify the checksum of the downloaded file.*

Open the command line in the Download folder:

**Windows**
[Shift]+[right-click] on the Download Folder and choose "open command window here" or "open power shell here". Substitute filename with the real filename of the downloaded file. 
```CertUtil -hashfile filename SHA256```

**Linux**
We assume you know what you are doing here. 😉
```sha256sum filename```

**MacOS**
Head into System Preferences and select Keyboard > Shortcuts > Services. Find "New Terminal at Folder" in the settings and click the box. Now, when you're in Finder, just right-click a folder and you're shown the services > to open Terminal. 
```shasum -a 256 filename```

Once done compare the output with the hash for your downloaded file from GitHub in the verification section of the release note.

**Downloads**

**Latest releases**

The all in one resource
<https://particl.io/downloads>

Particl Desktop (with Open Marketplace)
<https://github.com/particl/particl-desktop/releases/latest>

Particl Core (Qt) (with Ledger wallet support)
<https://github.com/particl/particl-core/releases/latest>

---

'!tag config'

**Particl's config folders location:**

_Particl Core Config Folder_

It holds the blockchain data, smsg data, logfiles for the blockchain relevant events, and all the wallets you create. 

_**Windows:**_ `%UserProfile%\AppData\Roaming\Particl`
_**MacOS:**_ `~/Library/Application Support/particl`
_**Linux:**_ `~/.particl`

_Particl Desktop Config Folder_

It may hold the Particl Desktop application itself and the particld deamon depending on your installation type.

_**Windows:**_ `%userprofile%\AppData\Roaming\Particl Desktop` AND ``%userprofile%\AppData\Local\Programs\Particl Desktop`
_**MacOS:**_ `~/Library/Application Support/Particl Desktop`
_**Linux:**_ `~/.Particl Desktop` OR `/opt/Particl Desktop`

_Particl Marketplace Config Folder_

It holds the marketplace database, marketplace logfiles, images, and your marketplace configurations eg. smsg key mappings to your wallet profile. 

_**Windows:**_ `%userprofile%\AppData\Roaming\particl-market`
_**MacOS:**_ `~/Library/Application Support/particl-market`
_**Linux:**_ `~/.particl-market`

_Particl Bot Folder_

It holds informations about bots and their configurations.

_**Windows:**_ `%userprofile%\AppData\Roaming\particl-bot`
_**MacOS:**_ `~/Library/Application Support/particl-bot`
_**Linux:**_ `~/.particl-bot`

---

'!tag howtoreport'

• **What is your environment?**
    - Operating System/Version: [*Windows 10*]
    - Particl Client/ Version: [*Desktop 2.3.4*]

• **What did you do and what do you expect?**
    - Try to explain the facts in short, coherent sentences.

• **Add additional evidence if possible and/or necessary.**
    - screenshots
    - debug.log
    - market.log

---

'!tag support'

**HELP | SUPPORT | HOWTO**

• _FAQ & Wiki_ <https://particl.wiki/support/start>
• _Tutorials_ <https://particl.wiki/tutorial/start>
• _Installation guide_ <https://particl.wiki/tutorial/particl-desktop/start>
• _Staking pools_ <https://particl.wiki/learn/staking/pools>
• _Report issues & contribute_ <https://github.com/particl/particl-desktop/issues>

**Dedicated support channels**

• Discord <https://discordapp.com/channels/391967609660112925/392014161523245105/> #support 
• Telegram <https://t.me/particlhelp>
• Element (Riot) <https://riot.im/app/#/room/#particlhelp:matrix.org> #particlhelp:matrix.org

---

'!tag scratchwindows'

**Start from scratch on windows**

* Shutdown any particl client
* rename all folders
* copy wallet.dat back (if you want to keep it)
* start particl client again (will start from scratch)

**This can be copy and pasted to the CMD console of windows**
```
ren "%UserProfile%\AppData\Roaming\Particl" _old_Particl
ren "%userprofile%\AppData\Roaming\particl-bot" _old_particl-bot
ren "%userprofile%\AppData\Roaming\particl-market" _old_particl-market
ren "%userprofile%\AppData\Roaming\Particl Desktop" "_old_Particl Desktop"
mkdir %userprofile%\AppData\Roaming\Particl
copy %userprofile%\AppData\Roaming\_old_Particl\wallet.dat %userprofile%\AppData\Roaming\Particl
```

---

'!tag timesync'

Time sync is a common problem of Windows and/or your PC under special circumstances. 

**Meanwhile**:
Click on the clock in the taskbar and select "Change date and time settings". Turn off "Set time automatically" and then turn it back on. This forces a resync.

**Force using NTP server**
Open a cmd prompt: *Press [Windows]+[R] to open the “Run” box. Type “cmd” into the box and then press [Ctrl]+[Shift]+[Enter] to run the command as an administrator.*

**Copy & Paste this into the cmd box**
```
net stop w32time
w32tm /config /syncfromflags:manual /manualpeerlist:"0.it.pool.ntp.org 1.it.pool.ntp.org 2.it.pool.ntp.org 3.it.pool.ntp.org"
net start w32time
w32tm /config /update
w32tm /resync /rediscover
```

Once done you can **automate this**. Copy & Paste this into the cmd box.
```
SCHTASKS /CREATE /SC MINUTE /MO 10 /TN "MyTasks\TimeSync10mins" /TR "w32tm /resync" /RU System
``` 

---

'!tag adhominem'

ad hominem
*You attacked your opponent's character or personal traits in an attempt to undermine their argument.*

Ad hominem attacks can take the form of overtly attacking somebody, or more subtly casting doubt on their character or personal attributes as a way to discredit their argument. 

The result of an ad hom attack can be to undermine someone's case without actually having to engage with it.

**Example**: After Sally presents an eloquent and compelling case for a more equitable taxation system, Sam asks the audience whether we should believe anything from a woman who isn't married, was once arrested, and smells a bit weird.

---

'!tag links'

<https://particl.io> - with :shopping_bags: Particl Marketplace -the leave no trace marketplace! 

:gem: Links <https://bit.ly/2KF4cTN> 
:postal_horn: News <https://particl.news>
:shopping_bags: Marketplace A to Z <https://bit.ly/2ryEiui>
:cold_face: ColdStaking <https://medium.com/@PART_BEN/f1b48ff3de9a>
:paperclip: Listing Explorer <https://www.demarkets.io/particl/explorer>
:detective: Download <https://particl.io/downloads>
:arrows_counterclockwise: U.S. enabled Exchange <https://www.probit.com/app/exchange/PART-BTC>
:sparkling_heart: Fundamentals & Values <https://bit.ly/2IsqPcH>

---

'!tag cliunlock'

Complete process of starting the daemon and unlocking the wallet for staking only. Additionally not exposing the data to the terminal history.
```
particld -daemon  [enter]
particl-cli -stdin [enter]
walletpassphrase [enter]
yourpassword [enter]
0 [enter]
true [enter]
[ctrl]+[d]
```
*walletpassphrase* is a command in this case. It has to be put the way it is stated here. *yourpassword* is your real password to unlock the wallet. Attention: This can fail here, if special characters are utilized. The zero utilized here indicates an infinite number of time the wallet keeps unlocked for staking only.

---

'!tag test'

ping .... pong .... 

https://tenor.com/view/cats-ping-pong-gif-8942945

---

`!tag mustfollowtwitter`

**Branded**

* https://twitter.com/ParticlProject
* https://twitter.com/particl_page
* https://twitter.com/ParticlCommunity
* https://twitter.com/demarkets
* https://twitter.com/ParticlTribe
* https://twitter.com/localparticl

**Active Individuals**

* https://twitter.com/crypt0guard
* https://twitter.com/rosierest3
* https://twitter.com/thegreatestdoc
* https://twitter.com/NewsCyberpunk
* https://twitter.com/quentinbdb
* https://twitter.com/BTCforGermans
* https://twitter.com/RobbinHoodie
* https://twitter.com/MBacoinin
* https://twitter.com/George87599066
* https://twitter.com/MoneyInBnkFrank
* https://twitter.com/MrCryptopoly
* https://twitter.com/c3lopetra
* https://twitter.com/acctualdadon
* https://twitter.com/AllienWorks
* https://twitter.com/zaSmilingIdiot
* https://twitter.com/Arantuil1

fin
