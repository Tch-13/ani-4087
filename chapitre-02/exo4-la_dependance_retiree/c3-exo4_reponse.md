L'exercice demande de créer un module qui dépend d'un autre, puis lier directement le projet au premier module.
Nous allons utiliser les bibliothèques pour lier.

Nous allons lier le projet à une bibliothèque biblio1,
Ensuite nous allons lier cette bibliothèques à une biblio2.
Le programme va appeler la biblio2, puis appeler la biblio1.




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

Build Order (3 projects):
  1. biblio1 [STATIC_LIB] →
  2. biblio2 [STATIC_LIB] (depends: biblio1) →
  3. MaSalle [WINDOWED_APP] (depends: biblio1, biblio2)


╔══════════════════════════════════════════════════════════════════════════════════════════════╗
║  Project: biblio1                                                          Kind: STATIC_LIB  ║
╚══════════════════════════════════════════════════════════════════════════════════════════════╝

ℹ Found 1 source file(s)
✓   [1/1] Compiled: biblio1.cpp
ℹ Linking...
✓ Built: bin\Debug\Windows\biblio1.lib

┌──────────────────────────────────────────────────────────────────────────────────────────────┐
│  ✓ Build Successful                                                             Time: 0.28s  │
└──────────────────────────────────────────────────────────────────────────────────────────────┘

╔══════════════════════════════════════════════════════════════════════════════════════════════╗
║  Project: biblio2                                                          Kind: STATIC_LIB  ║
╚══════════════════════════════════════════════════════════════════════════════════════════════╝

ℹ Found 1 source file(s)
✓   [1/1] Compiled: biblio2.cpp
ℹ Linking...
✓ Built: bin\Debug\Windows\biblio2.lib

┌──────────────────────────────────────────────────────────────────────────────────────────────┐
│  ✓ Build Successful                                                             Time: 0.22s  │
└──────────────────────────────────────────────────────────────────────────────────────────────┘

╔══════════════════════════════════════════════════════════════════════════════════════════════╗
║  Project: MaSalle                                                        Kind: WINDOWED_APP  ║
╚══════════════════════════════════════════════════════════════════════════════════════════════╝

ℹ Found 1 source file(s)
✓   [1/1] Compiled: main.cpp
ℹ Linking...
╔══════════════════════════════════════════════════════════════════════════════════════════════╗
║                                Compilation Error: Link Failed                                ║
╠══════════════════════════════════════════════════════════════════════════════════════════════╣
║ C:/msys64/mingw64/bin/../lib/gcc/x86_64-w64-mingw32/16.1.0/../../../../x86_64-w64-mingw32/bi ║
║ n/ld.exe:                                                                                    ║
║ C:\Users\Alan\Desktop\Jenga\MaSalle\bin\Debug\Windows\biblio2.lib(biblio2_biblio2.obj): in   ║
║ function `fonction2()':                                                                      ║
║ C:/Users/Alan/Desktop/Jenga/MaSalle/biblio2/biblio2.cpp:5:(.text+0x9): undefined reference   ║
║ to `fonction1()'                                                                             ║
║ collect2.exe: error: ld returned 1 exit status                                               ║
╚══════════════════════════════════════════════════════════════════════════════════════════════╝
✗ Link failed: bin\Debug\Windows\MaSalle.exe

┌──────────────────────────────────────────────────────────────────────────────────────────────┐
│  ✗ Build Failed                                                                 Time: 0.39s  │
│ Errors: 2  | Failed files: 1                                                                 │
└──────────────────────────────────────────────────────────────────────────────────────────────┘

════════════════════════════════════════════════════════════════════════════════
                                  BUILD FAILED
════════════════════════════════════════════════════════════════════════════════
Projects Built:  2/3
Failed:         1
Errors:         2
Time:           0.90s
Status:         ✗ FAILURE
════════════════════════════════════════════════════════════════════════════════

Echecs (1) — a corriger :
  ✗ MaSalle




L'erreur mentionne une erreur de liaison (le programme n'accède pas à une ressource demandée). 
Ainsi, des 4 étapes (préprocesseur, compilation, assemblage, édition des liens), 
il s'agit d'une erreur à l'édition des liens.
