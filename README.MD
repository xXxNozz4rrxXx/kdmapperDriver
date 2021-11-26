# KDMapper

Original creator https://github.com/z175

Updated and improved by https://github.com/TheCruZ

Mdl allocation writed by https://github.com/TygoL

Tested from **Windows 10 1607** to current **Windows 11 22449.1** :heavy_check_mark:

Update mainly done for UnknownCheats Forum https://www.unknowncheats.me/forum/members/1117395.html

KDMapper is a simple tool that exploits iqvw64e.sys Intel driver to manually map non-signed drivers in memory

**Note:** Add definition **DISABLE_OUTPUT** to remove all console outputs


## WHAT IS FACEIT AC?
Faceit is currently the most popular pugging website for a good reason. It has a good ranking system in which players quickly can get to a rank where they can play against opponents of similar skill. Not only is it a ranked league, Faceit also has an impressive anticheat which is honestly the main selling point. You could play Faceit for years and never play with a cheater. Or maybe you will but you probably wouldn't notice, even if you bypass the anticheat, if you rage you're gonna get reported and banned.

Faceit has the second best anticheat, ESEA is better.

As described on their site:

State of the art client side cheat detection combined with a unique server side analysis which improves detections as volume increases. Combination of several behavioral systems allows for continuous analysis of new cheats and automated update of cheat detection library. By relying on detections that are typical of today's client-side anti-cheats, we strive to improve our players’ experience and add another layer of protection to FACEIT. We have built the client using by combining all information we gather from different sources: the clientside & serverside anticheat along with the FBI system). This means our Data Science team can process and analyse all this data in real-time to keep improving and automating cheating detections. This is a long-term effort which we believe will eventually lead to detections that would not be possible with an approach limited to client-side detections.
What they ban for:
Cheats/Hacks (including skin changers, cheat loaders/drivers)
External scripting/macros designed to gain an advantage over other players (e.g. No recoil script, ...)
Use of any exploits to bypass the Anti-Cheat protection
Use of any (game) exploits to gain an unfair advantage (e.g. removing textures to see through walls, removing smoke grenades, ...)
Attempts to debug or modify the FACEIT Anti-Cheat
Running game inside a Virtual Machine
Usage of any methods/software to evade previous bans

## Features:
	
	Works with /GS- compiled drivers
	Hooks NtAddAtom which exists everywhere and is rarely called
	Clears MmUnloadedDrivers
	Clears PiDDBCacheTable
	Clears g_KernelHashBucketList
	Use NtLoadDriver and NtUnloadDriver for less traces
	Prevent load if \Device\Nal exists (Prevents BSOD)
	Header section skipped while copying driver to kernel
	Added param --free to automatically unmap the allocated memory
	Added param --mdl to map in mdl memory
	Added param --PassAllocationPtr to pass allocation ptr as first param
	Added the possibility to modify params before call driver entry
	Now you can pass directly bytes to mapdriver function
	
## Requirements:

    Set Custom Driver Entry Point
    Create a thread and return from driver entry fastest as you can to prevent unexpected calls

### Errors 0xC0000022 and 0xC000009A:
A lot of people ask me about this errors loading the vulnerable driver, both are caused by FACEIT AC since his driver is always running you have to uninstall it

Have Fun!!
