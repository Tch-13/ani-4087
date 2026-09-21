
 Alan@DESKTOP-T8COM2C MINGW64 ~/desktop/jenga/masalle (main)
$ jenga info

╔══════════════════════════════════════════════════════════════════╗
║                                                                  ║
║                ██╗███████╗███╗   ██╗ ██████╗  █████╗             ║
║                ██║██╔════╝████╗  ██║██╔════╝ ██╔══██╗            ║
║                ██║█████╗  ██╔██╗ ██║██║  ███╗███████║            ║
║           ██   ██║██╔══╝  ██║╚██╗██║██║   ██║██╔══██║            ║
║           ╚█████╔╝███████╗██║ ╚████║╚██████╔╝██║  ██║            ║
║            ╚════╝ ╚══════╝╚═╝  ╚═══╝ ╚═════╝ ╚═╝  ╚═╝            ║
║                                                                  ║
║             Multi-platform C/C++ Build System v2.8.0             ║
║                                                                  ║
╚══════════════════════════════════════════════════════════════════╝

=========================== Jenga Workspace: MaSalle ===========================

Location: C:\Users\Alan\Desktop\Jenga\MaSalle
Entry file: C:\Users\Alan\Desktop\Jenga\MaSalle\MaSalle.jenga
Configurations: Debug, Release
Platforms: Windows
Target OSes: Windows, Linux, macOS
Target Architectures: x86_64


Projects
------------------------------------------------------------
Name      Kind          Language   Test   External
==================================================
MaSalle   WindowedApp   C++        No     No


Available Toolchains
------------------------------------------------------------
Name       Family   Target OS   Arch     Env
==============================================
host-gcc   gcc      Windows     x86_64   mingw
mingw      gcc      Windows     x86_64   mingw


Daemon
------------------------------------------------------------
Status: Not running




La commande "jenga info" nous apprend :
- le chemin complet exact de notre projet
- le système depuis lequel le programme est éxecuté (windows)
- les toolchains disponibles (host-gcc , mingw)
- les propriétés du projet (le test, projet marqué externe)
- l'état du daemon (il n'est pas lancé)
