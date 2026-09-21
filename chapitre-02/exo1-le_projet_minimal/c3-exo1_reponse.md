1. Fichier du projet MaSalle.jenga (le contenu)

from Jenga import *

with workspace("MaSalle", location="."):
    configurations(["Debug", "Release"])
    targetoses([TargetOS.WINDOWS, TargetOS.LINUX, TargetOS.MACOS])
    targetarchs([TargetArch.X86_64])

    with project("MaSalle"):
        windowedapp()
        language("C++")
        cppdialect("C++17")
        location(".")
        files(["src/**.cpp"])

        targetdir("bin/%{cfg.buildcfg}/%{cfg.system}")
        objdir("obj/%{cfg.buildcfg}/%{cfg.system}")

        with filter("system:Windows"):
            links(["user32", "gdi32", "opengl32"])

        with filter("system:Linux"):
            links(["pthread", "X11", "GL"])



2. Sortie de Jenga Build
Alan@DESKTOP-T8COM2C MINGW64 ~/desktop/jenga/masalle (main)
$ jenga build

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

Loading workspace...

Configuration: Debug
Target:        Windows x86_64
Toolchain:     mingw

Build Order (1 projects):
  1. MaSalle [WINDOWED_APP]


╔══════════════════════════════════════════════════════════════════════════════════════════════╗
║  Project: MaSalle                                                        Kind: WINDOWED_APP  ║
╚══════════════════════════════════════════════════════════════════════════════════════════════╝

ℹ Found 1 source file(s)
✓   [1/1] Compiled: main.cpp
ℹ Linking...
✓ Built: bin\Debug\Windows\MaSalle.exe

┌──────────────────────────────────────────────────────────────────────────────────────────────┐
│  ✓ Build Successful                                                             Time: 0.43s  │
└──────────────────────────────────────────────────────────────────────────────────────────────┘

════════════════════════════════════════════════════════════════════════════════
                                BUILD COMPLETED
════════════════════════════════════════════════════════════════════════════════
Projects Built:  1/1
Time:           0.43s
Status:         ✓ SUCCESS
════════════════════════════════════════════════════════════════════════════════




