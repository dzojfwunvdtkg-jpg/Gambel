# Nucleus Gamble (Fabric, Minecraft 26.2)

Client-Mod für **Hypixel SkyBlock**: Wenn du einen Crystal-Nucleus-Run abschließt, liest die Mod
Hypixels Chat-Block **CRYSTAL NUCLEUS LOOT BUNDLE → REWARDS** und spielt ein **Case Opening** ab:

1. Eine Walze mit Karten in Rarity-Farben rast vorbei, tickt bei jeder Karte und wird langsamer
2. Ab und zu fliegen Jackpots vorbei (★ Divan's Alloy, Quick Claw, Jade Dye …), manchmal landet einer knapp daneben
3. Sie bleibt auf deinem **echten besten Drop** stehen, mit Lichtblitz und Sound
4. Danach siehst du deine komplette Beute, dann blendet alles aus

**Das Ergebnis ist immer dein echter Loot.** Die vorbeifliegenden Karten sind nur Deko.
Der dunkle Hintergrund verdeckt den Chat, damit der Loot nicht vorher gespoilert wird.

## Ist das erlaubt?

Die Mod **liest nur den Chat und zeichnet ein Overlay**. Sie sendet nichts, klickt nichts,
verändert keine Pakete und nutzt keine Mixins. Sie ist damit eine reine Anzeige-Mod wie viele andere
SkyBlock-Mods. Garantie gibt es bei Hypixel aber nie: Hypixel entscheidet selbst, was erlaubt ist.

## Bauen (die .jar erstellen)

### Variante A: ohne etwas zu installieren (GitHub)
1. Kostenlosen GitHub-Account anlegen, neues Repository erstellen
2. Alle Dateien aus diesem Ordner hochladen (auch den versteckten Ordner `.github`)
3. Oben auf **Actions** → **Build Mod** → **Run workflow**
4. Wenn es durch ist (grüner Haken): auf den Lauf klicken, unten bei *Artifacts* **nucleusgamble-jar** herunterladen
5. Die ZIP entpacken. Drin liegt `nucleusgamble-1.0.0+26.2.jar`

### Variante B: auf deinem PC
1. **Java 25 JDK** installieren (z. B. Temurin von adoptium.net)
2. In diesem Ordner ein Terminal öffnen
3. Windows: `gradlew.bat build` · Mac/Linux: `./gradlew build`
4. Die Mod liegt danach in `build/libs/` (nimm die Datei **ohne** `-sources`)

## Installieren
1. Fabric Loader für **Minecraft 26.2** installieren (oder ein Profil in der Modrinth App / Prism Launcher anlegen)
2. **Fabric API** für 26.2 in den `mods`-Ordner
3. `nucleusgamble-…jar` in den `mods`-Ordner
4. Im Spiel testen: **`/nucleusgamble test`**

## Befehle

| Befehl | Was es macht | Standard |
|---|---|---|
| `/nucleusgamble` | Einstellungen anzeigen | |
| `/nucleusgamble test` | Animation mit Fake-Loot abspielen | |
| `/nucleusgamble stop` | Laufende Animation abbrechen | |
| `/nucleusgamble toggle` | Case Opening an/aus | an |
| `/nucleusgamble sound` | Sounds an/aus | an |
| `/nucleusgamble time <2-20>` | Wie lange die Walze dreht (Sekunden) | 7 |
| `/nucleusgamble reveal <1-30>` | Wie lange das Ergebnis stehen bleibt | 5 |
| `/nucleusgamble tease <0-100>` | Wie oft ein Jackpot knapp daneben landet (%) | 20 |

Einstellungen werden in `config/nucleusgamble.properties` gespeichert.

## Gut zu wissen
- Welcher Drop "der beste" ist, wird über die Drop-Chancen aus dem SkyBlock-Wiki geschätzt
  (seltener = besser). Unbekannte Items werden nach ihrer Rarity-Farbe bewertet.
- Wenn eine andere Mod (z. B. ein Chat-Filter von SkyHanni) den Loot-Block versteckt oder zusammenfasst,
  kann die Mod ihn eventuell nicht lesen. Dann den Filter für den Nucleus-Loot ausschalten.
