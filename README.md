# g0blin

(WIP) jailbreak for iOS 10.3.x on A7-A9 devices

updated v0rtex exploit + yalu102 kpp bypass

## Entitlement temp fix
- download & install Filza from Cydia
- download http://www.mediafire.com/file/bv129w6k80cds60/ent.xml on your mobile device and open it with Filza
- ent.xml should now be in /var/mobile/Documents
- now ssh into your device
- type in "cd /Applications/Filza.app/ && ldid -e Filza /var/mobile/Documents/FilzaEnts.xml" without ""
- add "<key>com.apple.private.security.no-container</key>
        <true/>"
        to every 
        ```<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/Proper$
           <plist version="1.0">
           <dict>``` inside /var/mobile/Documents/FilzaEnts.xml using Filza
- to fix Filza type in "cd /Applications/Filza.app/ && ldid -S/var/mobile/Documents/FilzaEnts.xml Filza" Without ""
- respring and Filza should have root permissions

To fix it for other Applications type in  "cd /Applications/YOURAPPNAME.app/ && ldid -e/var/mobile/Documents/YOURAPPNAME.xml YOURAPPNAME" Without ""
replace YOURAPPNAME with the app you want to fix and follow the other steps on the filza one.

##Entitlement Temp Fix(Old)
If you've used the old fix, most entitlements the app needs are **gone**! but fear not.
Reinstall the app and follow the new instructions.

## what works
- tfp0
- kernel r/w access
- remount / as r/w
- amfi patched
- starts an ssh server listening on port 2222
- command line tools to install packages (dpkg, apt-get if you install it)
- Substrate
- Cydia can now install tweaks

## what doesn't work
- GUI apps that need root priveledges are experiencing a sandbox error
- Filza can be fixed by applying the same extra entitlement given to Cydia


thanks to everyone helping out, finding offsets, testing, etc!

creds: Lucky Tobasco, Sizuga, Xenu, Saurik
