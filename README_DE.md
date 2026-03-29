[Deutsche Version](README_DE.md) | [English Version](README_EN.md)

---

# EcoDive: Save The Ocean
**Entwickler:**
- Michael Feldmann 
- Philipp Geier
- Jan Niclas Ruppenthal

Dieses Projekt ist das Abschlussprojekt des Moduls "VR und 3D-Interaktionen". Zusätzlich wurde es auch als Demo bei der VRST 2024 eingereicht.

## Beschreibung des Spiels
In unserem Spiel EcoDive muss der Spieler oder die Spielerin Müll in einer Unterwasserwelt aufsammeln. Die Bewegung erfolgt durch die Steuerung eines Diver Propulsion Vehicles (DPVs) und mithilfe eines Radars kann der Müll geortet sowie aufgesammelt werden.
Jedoch kann man in diesem Spiel nicht gewinnen, und es ist auch unabhängig davon, wie viel Müll vorher eingesammelt wurde. Diese Mechanik soll die Sinnlosigkeit des Müllsammelns verdeutlichen. Es soll verdeutlicht werden, dass der Abfall gar nicht erst in die Meereswelten gelangen sollte.

## Auswahl der Themen
Für unser Spiel haben wir uns für die folgenden Themen entschieden:
- Nachhaltigkeit
- Förderung von Empathie
- Bildung und Aufklärung

## Technischer Aufwand
Unser Spiel EcoDive beinhaltet eine Simulation von über 3000 Korallen und wir haben eine unendliche Generierung der Landschaft implementiert. Für die Meereslebewesen wurde eine Simulation eines einfachen Schwarms implementiert, damit die Unterwasserwelt immersiv und authentisch wirkt.

## Vermittlung der Inhalte
Um den Inhalt des Spiels so authentisch und immersiv wie möglich zu vermitteln, wird die Sicht durch den Einsatz eines Nebels und einer allmählichen Graufärbung durch Post-Processing verschlechtert. Die Lebendigkeit der Meereslebewesen (Fische, Korallen und Schildkröten) ist von der Aktivität des Spielers oder der Spielerin abhängig: Je weniger Müll aufgesammelt wird, desto mehr Lebewesen sterben. Zur Steigerung der Immersion des Spiels wird der Atem durch eine Sinuskurve oder durch die Mikrofoneingabe simuliert. Hierbei wird dieser durch ein Partikelsystem visualisiert. Am Ende des Spiels befindet man sich in einem Raum, in dem ein Faktenvideo abgespielt wird. Das Video soll über die Problematik des Meeresmülls und dessen weitreichende Auswirkungen aufklären.

## Nutzbarkeit und Benutzererfahrung
Um den Abfall in der Unterwasserwelt zu orten, kann man das Radar am linken Controller verwenden. Zur besseren Sichtbarkeit des Mülls in der Nähe von bunten Korallen wurde diesen Objekten eine rote Outline hinzugefügt. Die Bewegung erfolgt durch Pointing-based Steering mit 3-DOF-Translation und physischer Rotation durch eine lineare Funktion mit einer Maximalgeschwindigkeit von 5 m/s. Das Spiel kann am Ende durch einen Button neu gestartet werden.

## Einsatz von 3D-Interaktionen und multimodalem Feedback
Der Abfall kann mit den Controllern gegriffen und aufgesammelt werden. Während der Bewegung durch die simulierte Unterwasserwelt vibrieren die Controller in Abhängigkeit von der aktuellen Geschwindigkeit.

## Tastenbelegung
- **Greifen**: Den Abfall und den Griff des DPVs kann man mithilfe der Greiftaste greifen.
- **Fortbewegung**: Wenn man mit mindestens einem Controller das DPV greift, kann man mithilfe des rechten Triggers die Geschwindigkeit des DPVs einstellen.
- **Drehen**: Falls ein sicheres physisches Drehen nicht gewährleistet ist, kann der Stick am rechten Controller für eine horizontale Drehung genutzt werden.
- **UI-Interaktion**: Durch das Drücken eines Buttons des UIs mit dem Controller.


# Verwendete externe Ressourcen:

## Virtual Reality und 3D Interaktionen:
- XR Interaction Toolkit


## Sound waehrend des Spiels:
- Ambiente: https://freesound.org/people/Xemptful/sounds/406623/
- Luftblasen : https://freesound.org/people/ristooooo1/sounds/539819/?page=2#comments

## Spielszene:
- Lebewesen
    - Schildkroete: https://sketchfab.com/3d-models/sea-turtle-23dcb315dea44f5082b020b04710bd31
    - Fisch: https://assetstore.unity.com/packages/3d/characters/animals/fish/emperor-angelfish-263329
    - Korallen 01: https://sketchfab.com/3d-models/koraller-snm21005-d385ddbdef4340a2b0ee48eab81b785f
    - Korallen 02: https://sketchfab.com/3d-models/lowpoly-coral-pack-29d5be0e220f48818346cabfa065e887

    - Muell:
        - Muellsack: https://sketchfab.com/3d-models/low-poly-trash-bag-69876d51e2f0462498b81dffe3387ae0#download
        - Dosen: https://sketchfab.com/3d-models/tin-cans-ff0665ece31d4c4eb6182a4756c583bf
        - Kefir: https://sketchfab.com/3d-models/kefir-bottle-fe82b4f4286a48f294ebf05f8d264691
        - Joghurt: https://sketchfab.com/3d-models/yogurt-7cf010b5a4d245c8ae07be585aadc2b8#download
        - Flasche: https://sketchfab.com/3d-models/bottle-f06024f0949b4f78afd60b879fee9de9
        - Zerbeulte Dose: https://assetstore.unity.com/packages/tools/modeling/mess-maker-free-213803

## Game Over Raum (Video und Sound):
- Bilder:
    - https://pixahive.com/photo/__trashed-32113/
    - https://pixahive.com/photo/plastic-bottle-and-plastic-bags-on-ocean-floor/
    - https://pixahive.com/photo/a-polluted-river-8/
    - https://pxhere.com/en/photo/1365482
    - https://pxhere.com/en/photo/558663
    - https://pxhere.com/en/photo/1611355
    - https://pxhere.com/en/photo/428305
    - https://pxhere.com/en/photo/1414425
- Fakten:
    - https://en.nabu.de/topics/ecosystems/ocean-trash.html
    - https://www.unep.org/plastic-pollution
    - https://www.europarl.europa.eu/pdfs/news/expert/2018/10/story/20181005STO15110/20181005STO15110_en.pdf
    - https://www.science.org/doi/10.1126/science.aar3320
- Sound: https://freesound.org/people/guitarman213/sounds/707899/

## Sonstige Ressourcen:
- Quick Outline: https://assetstore.unity.com/packages/tools/particles-effects/quick-outline-115488
- Mass Spawner: https://assetstore.unity.com/packages/tools/terrain/mass-spawner-object-placement-tool-191111
- Zweiseitige Shader: https://assetstore.unity.com/packages/vfx/shaders/free-double-sided-shaders-23087
- Post Processing
- TextMeshPro