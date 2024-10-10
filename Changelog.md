# Gothic MDK Changelog


## v1.4 // 13.10.2022

* update the introduction from Alex by combining it  
  with the slightly different alex.txt provided by Tom
* added _config.yml for jekyll
* renamed documents -> docs
* added new webpage (index) and style.css


## v1.3 // 12.02.2021

Version 1.3 integrates all animations,  
morph-meshes and worlds in decompiled form.

Flosha: added copyright/authors list to tools/

Flosha: added alex.txt (thanks to Tom Putzki)  
        to the mdk-introduction

Avallach: Animations decompiled from  
GOTHIC using Gothic Sourcer 3.14:
  * ASC_ANIMS 
  * ASC_BODIES 
  * ASC_MOBSI 
  * ASC_MORPHMESH
  * ASC_OVERLAY
  * ASC_STATIC
  * MDS_MOBSI
  * MDS_OVERLAY

Avallach: Some zen files, not yet part of the  
official MDK, extracted by using GothicVDFS:
  * FIRETREE_LARGE.ZEN
  * FIRETREE_MEDIUM.ZEN
  * FIRETREE_MEDIUM_DUNGEONS.ZEN
  * FIRETREE_MEDIUM_LIGHT_ONLY.ZEN
  * FIRETREE_MEDIUM_WO_LIGHT.ZEN
  * FIRETREE_PSI_MEDIUM.ZEN
  * FIRETREE_SMALL.ZEN
  * FREEMINE.ZEN
  * ITLSTORCHBURNING.ZEN
  * OLDMINE.ZEN
  * ORCGRAVEYARD.ZEN
  * ORCTEMPEL.ZEN
  * WORLD.ZEN


## v1.2 // 29.02.2020

Flosha: v1.2 integriert primär diverse Tools,  
die innerhalb der Community entwickelt wurden.

* GothicVDFS aktualisiert (v1.5 -> v1.6.2)

* VDFS-Tool/ umbenannt in tools/  
  (Hierarchie von Nico übernommen) 

* 3DS MAX Stuff/ verschoben in tools/
* Milkshape 3D Stuff/ angelegt in tools/
* Blender Stuff/ angelegt in tools/

New tools included:  
  * GoMan 0.93 
  * GothicZTEX Decompressor 1.2.1 
  * ZTEX Tools 1.0
  * GothicVdfsOpt 1.0                                
  * Sprachausgabenhelfer 2.1
  * ZEN Convert
  * GothicSourcer 3.14 
  * Output-Commander 2.0
  * VDFManager 1.02 
  * Farbeimer
  * GVE (Gothic Variables Editor)
  * Stampfer 
  * Redefix 2.1 
  * FNTEdit 1.07
  * NPC-Viewer 1.0.0.0
  * Font2Targa 1.1
  * zSlang
  * Spacer Hotkeys
  * ZenVis 1.8.2

New plugins added:  
  * MilkShape 3D Import/Export PlugIn for GOTHIC 3DS (Nico)
  * Kerrax Imp/Exp 3DSMax5 & 3DSMAX 6-8 (3DS Max Stuff/Plugins)
  * Unrecorded List Exporter Plugin für den Output-Commander
  * Gothic MaT-Blender 1.3 (Blender Stuff)
  * KerraxImpExp. Blender 2.78 (fix)

Fixed some grammar in the german documentation  
Added ZTEX documentation (misc/ZTEX file reference)  
Added Gothic versions document (misc/GothicVersions) 

Added armors in .asc format (_work/data/Anims/asc_bodies/armor)  

Added Daedalus Syntax Highlighting (misc/) for:
  * CodeEdit
  * CrimsonEditor
  * Notepad++
  * SourceEdit
  * UltraEdit
  * VSCode

Flosha: Spacer Fix 1.51:  
  Das in 1.50 eingeführte Signal beim Abschluss von  
  Operationen ist jetzt weniger schrill (system/ready.wav)  
  (Wenn ihr euch ein anderes Signal wünscht (default ist  
  _work/data/sound/sfx/inv_open.wav), einfach ready.wav  
  unter system/ durch euer gewünschtes Signal ersetzen)  

Flosha: Releases.txt angelegt (dokumentiert die Release  
  Dates diverser Komponenten des DevKits unter /tools)  

Flosha: WorldofGothicLinks.txt angelegt (Linkliste zu den  
  Releasethreads der Tools im World of Gothic Forum)  


## v1.1 // 19.02.2020

Flosha: v1.1 integriert alle offiziellen Updates.

* Spacer Update 1.50 hinzugefügt (spacer.exe und  
  ready.wav in [GOTHIC]system); dieses Update verbessert  
  die Benutzerführung im Spacer. Hier die Fixes:  
     - "Division By Zero" abgefangen
     - Positionierung der Kamera bei Doppelklick  
       auf Objekt im Objektbaum gefixt
     - Die Tastatur hat sich oft "verhakt", wenn man mit  
         SHIFT+ZIFFERNBLOCK durch die Level raste.  
         Die Ursache ist, dass bei gedrückter SHIFT-Taste sich der 
         Ziffernblock komplett dämlich verhält: 
         Es kommen pro Tastendruck immer zwei KeyDowns beim 
         Tastaturhandler an. Deshalb folgende Maßnahmen:
         - Bewegen mit Ziffernblocktasten entfernt. 
           Ebenso die ALT-Taste (Sidestep)
         - STRG-Taste in Kombination mit Cursortasten führt nun zu 
           LINK/RECHTS-Bewegungen (Sidestep)
         - Außerdem: Die Bewegungsgeschwindigkeit kann mit PAD_UP 
           / PAD_DOWN geändert werden.
     - Der Spacer "versteckt" sich bei längeren Operationen wie 
       Laden, Speichern und Kompilieren weitgehend bis er fertig 
       ist. Beim Abschluss gibt er ein Ton-Signal. ("ready.wav")
     - Maximieren des Spacerfensters ist nun nicht mehr möglich 
       (auch bei Doppelklick auf die Titelleiste), dafür kann man 
       jetzt das Fenster Minimieren. Die Berechnung der 
       Fenstergröße bei Auflösungsänderung wurde auch gefixt
     - Fehlermeldungen erscheinen in jedem Fall im Vordergrund 
       (TOPMOST), so dass sie nicht mehr übersehen werden können
     - Zusatz "as child" im Menü beim Einfügen eines neuen Vobs 
       als Kind eines anderen Vobs

* Dokumentation um Spacer Tutorial erweitert (c)BertSpeckels

* MATLIB (Materialbibliothek für den Spacer) integriert


## v1.0 // 26.05.2002

Release by Piranha Bytes.