1- Code dans MaSalle.jenga
from Jenga import *

with workspace("MaSalle", location="."):
    configurations(["Debug", "Release"])

    with project("MaSalle"):
        consoleapp()      
        language("C++")
        cppdialect("C++17")
        location(".")
        files(["src/**.cpp"])

        targetdir("bin/%{cfg.buildcfg}/%{cfg.system}")
        objdir("obj/%{cfg.buildcfg}/%{cfg.system}")

        # Condition fausse avec un système Windows (on remplacera Linux par Windows après)
        with filter("system:Linux"):
            defines(["MON_DEFINE_TEST"])


2. Fichier d'execution src/main.cpp
#include <cstdio>

int main() {
#ifdef MON_DEFINE_TEST
    std::printf("DEFINE PRESENT\n");
#else
    std::printf("DEFINE ABSENT\n");
#endif
    return 0;
}

3- Les différentes sorties 
  a- avec condition fausse (`system:Linux`)
    DEFINE ABSENT
  b-avec condition vraie (`system:Windows`)
    DEFINE PRESENT

4- Remarque
La commande "jenga info" retourne une sortie qui n’affiche jamais les définitions contenues dans le programme.
Seul le programme lui-même peut révéler si un filtre a été appliqué.
