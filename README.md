# xsvpn-helper

Scripts om via Viscosity op een Mac de verbinding naar vpn.xs4all.net te maken
en te verbreken.

Eerst gemaakt om problemen met corrupte backups tegen te gaan, later ook de vpn verbinding
opzetten uit luiheid, en omdat het kan... ("xsvpn" bevat een browser geschreven in zo'n
hondertal bashregels...).

Een TimeMachine backup is een encrypted image (HDI image) op een remote disk, gemount via
een VPN. Als je hard je VPN afbreekt, is de kans op corruptie op het encrypted filesystem
enorm groot, en krijg je de gevreesde "To improve reliability, Time Machine must create a new
backup for you.", waarop je al je huidige backups kwijt bent.

"netjes" je backup afsluiten en disks unmounten is de oplossing.

* xsvpn

Zet connectie naar vpn.xs4all.net op, gebruikt bestaande verbinding (die nog minimaal
8 uur geldig is, zie constante bovenin programma), of vraagt credentials voor nieuwe
connectie download.

* gottago

Script om netjes je backup af te sluiten, en disks te unmounten, zodat je je laptop
kunt dichtklappen.

* tm-delete-stale

Script om half-opgeruimde TimeMachine snapshots te wissen. Soms vergeet MacOS om TimeMachine
snapshots helemaal weg te halen, er blijft dan een directory over die niet als snapshot
gebruikt kan worden, maar die wel ruimte inneemt. Bijvoorbeeld als je tijdens de cleanup
een netwerk issue hebt of je laptop dichtklapt. Dit script zoekt die half gedelete directories
op en haalt ze netjes weg.

* fix-time-machine-sparsebundle-nas-based-backup-errors.html

Webpage over hoe je errors in je TimeMachine zelf kunt fixen, via fsck\_hfs, hoewel
dat enorm lang duurt. Ik heb hier zelf allerlei aantekeningen aan toegevoegd.
Origineel van:
https://www.garth.org/archives/2011,08,27,169,fix-time-machine-sparsebundle-nas-based-backup-errors.html

