graphics_Intel_framebuffers
============
OS X Intel HD Graphics

OS X HD4600+/HD4000/HD3000 Framebuffer Edits
Find HD4600+/HD4000 HDMI port-number (HD3000 similar)
Match motherboard connector to framebuffer connector
Enable multiple display support

Requirements
1. Desktop only
2. Mavericks 10.9 or newer
3. Intel HD Graphics/kext/framebuffer
   1. HD4600+/Azul/AAPL,ig-plartform-id/03 00 22 0d
   2. HD4000/Capri/AAPL,ig-plartform-id/0a 00 66 01
   3. HD3000/SNB/AAPL,snb-platform-id/10 00 03 00
4. Framebuffer Injection
   1. HDMI audio dsdt/ssdt
   2. Chimera (Azul/Capri/SNB)
      1. IGPEnabler=Yes
   3. Chameleon
      1. IntelAzulFB/10
      2. IntelCapriFB/10
   4. Clover TBA

More Information
1. HD4600+/HD4000/HD3000 Framebuffer Edits.pdf

Framebuffer Configurations
Connector/Port__|Port 0x5_______|Port 0x6_______|Port 0x7_______|
Native SNB/Capri|DP or ND_______|DP or ND_______|HDMI___________|
Native Azul	|DP or ND_______|DP or ND_______|DP or ND_______|
a SNB/Capri/Azul|DP or ND_______|HDMI/DVI*______|HDMI/DVI*______|
b SNB/Capri/Azul|HDMI/DVI*______|DP or ND_______|HDMI/DVI*______|
c Azul		|HDMI/DVI_______|HDMI/DVI_______|DP or ND_______|
d Azul		|HDMI/DVI_______|HDMI/DVI_______|HDMI/DVI_______|
e Azul		|DP or ND_______|HDMI/DVI_______|DP or ND_______|
DVI* - Azul only, HDMI - SNB/Capri/Azul, DVI - SNB/Capri (NA)

Framebuffer Edit Scripts
   1. HD4600/Azul
        a - graphics_intel_hd5k-azul-a-90_patch.command
	b - graphics_intel_hd5k-azul-b-90_patch.command
	c - graphics_intel_hd5k-azul-c-90_patch.command
	d - graphics_intel_hd5k-azul-d-90_patch.command
	e - graphics_intel_hd5k-azul-e-90_patch.command
   2. HD4000/Capri
	a - graphics_intel_hd4k-capri-a-90_patch.command
	b - graphics_intel_hd4k-capri-b-90_patch.command
   3. HD3000/SNB
	a - graphics_intel_hd3k-snb-a-90_patch.command
	b - graphics_intel_hd3k-snb-b-90_patch.command

Installation
  1. Download script, github.com/toleda/graphics_Intel.......patch.command
  2. Downloads/graphics_Intel.......patch.command  (Do not move file)
     1. Double click on file name
     2. Enter Password
     3. No errors, restart
	1. Terminal Report:
	Last login: Mon Feb 17 18:10:57 on console
	Downloads/HD4600+\:Azul\ Edit/graphics_intel_hd5k-azul-a-90
	  _patch.command ; exit;
 	graphics_intel_hd5k_azul-a-90_patch.command_v2.0
	Copy S/L/E/AppleIntelFramebufferAzul.kext to Desktop.
	Password:
	Fix permissions ...
	Kernel cache...
	Finished, restart required.
	logout
	
	[Process completed]

Tools
1. IOReg
   1. IOReg (View Raw) - https://github.com/toleda/audio_ALCInjection/blob/master/IORegistryExplorer_v2.1.zip
   2. IOJones - http://ge.tt/api/1/files/6C79yoh/0/blob?download

Restore Native Framebuffer kext
1. Desktop/AppleIntel....-orig.kext
2. Rename AppleIntel....-orig.kext to AppleIntel.....kext
3. Install with Kext Installer (Kext Utility, DCPIManager, KextBeast, etc.)

Problem Reporting (include the following information)
1. Description of HDMI audio problem
   1. OS X version/motherboard model/BIOS version/processor/graphics
   2. Procedure/Guide Used
   3. Copy of IOReg - IOReg_v2.1/File/Save a Copy As…, verify file (no ioreg.txt)
   4. EFI/Clover/config.plist
   5. EFI/Clover/ACPI/Patched/dsdt.aml (if installed)
   6. EFI/Clover/ACPI/Patched/ssdt.aml (if installed)
2. Post to:
   1. http://www.tonymacx86.com/hdmi-audio/112469-mavericks-hdmi-audio-applehda.html
   2. http://www.insanelymac.com/forum/topic/292999-mavericks-applehda-hdmi-audio/

Credit bcc9: http://www.insanelymac.com/forum/topic/259705-editing-custom-connectorinfo-for-intel-hd-3000-graphics-sandy-bridge-osx-lion/

toleda
https://github.com/toleda/graphics_Intel_framebuffers