[Deutsche Version](README_DE.md) | [English Version](README_EN.md)

---

# Locomotion und das Einkaufszentrum
**Entwickler:**
- Michael Feldmann 
- Philipp Geier
- Jan Niclas Ruppenthal

## Beschreibung der Übung
In dieser Übung sollten wir ein körperbasiertes und egozentrisches Bewegungsinterface implementieren. Dabei soll dieses Interface zu unserem gewählten Szenario bzw. Umgebung passen. 
Hierbei haben wir uns für ein Einkaufszentrum als Umgebung entschieden und man bewegt sich mithilfe eines Segways durch das Gebäude, um vier geforderte Artikel so schnell wie möglich einzukaufen.


---

## Aufgabenteil a)

### Fortbewegungsaufgabe
In dieser Aufgabe erhalten Sie nach einem harten Arbeitstag eine Liste mit vier verschiedenen Artikeln, die Sie noch einkaufen müssen. Dummerweise gibt es nur ein einziges Kaufhaus, das diese momentan auf Lager hat. Da für dieses Kaufhaus morgen ein Umbau bevorsteht, steht nur noch ein Exemplar von diesen Artikeln zur Verfügung. 

Ihr Ziel ist es, alle benötigten Artikel einzusammeln. Die vier Artikel werden bei jedem Start randomisiert ausgewählt. Es wird dabei zugesichert, dass Sie auf beiden Etagen genau zwei Artikel sammeln müssen. Somit müssen Sie mindestens einmal mit der Rolltreppe fahren.

### Verwendete Locomotion
* **Metapher:** Steering-Leaning
    * *1 DOF vTranslation:* Durch Lehnen wie ein "Human Joystick" entlang der Z-Achse.
    * *1 DOF vRotation:* Durch Bewegen der Controller bzw. der physischen Stange entlang der X-Achse.
* **Travel Task:** Search
* **Funktionen:**
    * *Leaning (Translation):* Powerfunktion mit einer Deadzone von 5 cm. Maximalgeschwindigkeit: 5 Meter pro Sekunde nach 34,8 cm.
    * *Steering (Rotation):* Powerfunktion mit einer Deadzone von 10 cm. Maximalgeschwindigkeit: 30 Grad pro Sekunde nach 28,3 cm.

### Testen der Aufgabe und der Locomotion
*Durchgeführt im Stehen durch Michael Feldmann und Jan Niclas Ruppenthal*

Beide Tester sollten die Aufgabe dreimal durchführen. Dabei haben beide nach dem zweiten Durchlauf abgebrochen, da wir bemerkt haben, dass unsere Rotation Cybersickness verursacht. Um dies ein wenig zu lindern, haben wir die Rotationsgeschwindigkeit von 45 Grad pro Sekunde auf 30 Grad pro Sekunde gesenkt. Zudem kann man die Locomotion auch sitzend verwenden, um Cybersickness vorzubeugen, auch wenn man ein Segway normalerweise im Stehen betreibt.

Die Translation über das Lehnen konnte von beiden gut bedient werden und die Aufgabe ließ sich sehr schnell lösen. Auf der Rolltreppe wird die Locomotion deaktiviert. Dies fanden beide gut, da es als kurze Ruhepause dienen konnte. Des Weiteren vibrieren die Controller während der Fahrt auf der Rolltreppe. Wenn die Vibration nachlässt, ist das ein Indikator für den Nutzer, dass die Locomotion wieder eingeschaltet ist. Bis auf die Rolltreppe erzielen wir eine hohe Nutzerfreiheit.

---

## Aufgabenteil b)

### Wieso wurde dieses Interface implementiert?
Wir haben eine uns bekannte Fortbewegungsmethode gesucht, die mit Kopf- und Handbewegungen gleichzeitig gesteuert werden kann. Dabei wollten wir auch etwas Bekanntes für die Immersion verwenden. Durch die Inspiration eines Segways ist das Interface zudem einfacher zu erlernen.

### Stärken des Interfaces
* **Multimodale Interaktion:** Die Vibration der Controller wird je nach Geschwindigkeit des Segways stärker oder schwächer. Durch die physische Stange kann die Vibration der Controller zusätzlich verstärkt werden.
* **Immersion:** Da wir uns für ein plausibles Szenario entschieden haben, erzielen wir eventuell eine höhere Immersion.
* **Präzision:** Durch die Verwendung einer Powerfunktion sowohl für die Translation als auch für die Rotation wird eine höhere Präzision bei der Fortbewegung erzielt.
* **Deadzone:** Wir haben uns für eine Deadzone entschieden, damit man sich nicht bei jeder kleinen Bewegung des Kopfes, der Controller oder der physischen Stange direkt virtuell bewegt.

### Schwächen des Interfaces
* Eine physische Rotation des gesamten Körpers macht das Interface kaputt.
* Auch wenn wir die Rotationsgeschwindigkeit verringert haben, verursacht sie teilweise immer noch Cybersickness.
* Eine virtuelle vertikale Bewegung ist nur begrenzt möglich (nur über die Rolltreppe). Diese ist jedoch statisch, da die Locomotion dort ausgeschaltet wird.
* Unsere Methode ist nicht gut auf weite Größen skalierbar. Wir können für große Distanzen nicht einfach die Maximalgeschwindigkeit erhöhen, da der Nutzer sonst die Kontrolle über das Segway verliert und die Cybersickness zunehmen könnte.
* Durch die virtuelle mittlere Stange des Segways kommt es zu einem leichten Verlust der Immersion.
* Die Controller müssen von der Quest 3 getrackt werden. Falls das Tracking fehlschlägt, kann das Interface nicht genutzt werden.

### Messung der Performance und Nutzbarkeit
**Performance:**
* Wir können für jeden Probanden die benötigte Zeit messen.
* Wir loggen die Anzahl der Kollisionen mit Wänden oder anderen Objekten. Eine hohe Anzahl an Kollisionen deutet darauf hin, dass der Nutzer seine Umgebung nicht gut wahrnehmen konnte.

**Nutzbarkeit (Usability-Studie):**
* Probanden führen die Einkaufsaufgabe durch und müssen sich merken, wo sie die passenden Artikel gefunden haben.
* Die Nutzbarkeit kann nach der Aufgabe mit standardisierten Fragebögen wie der System Usability Scale (SUS) oder dem NASA-TLX bewertet werden.
* Diese Studie lässt sich durch einen Vergleich erweitern: Unsere Methode könnte mit anderen Interfaces wie z. B. Pointing-based Steering oder Redirected Walking verglichen werden.

---

## Starten des Projekts

Wenn Sie unser Unity-Projekt geöffnet haben, müssen Sie Unity eventuell mehrmals neu starten.

Beim ersten Start des Editors erscheint möglicherweise eine Meldung, dass Veränderungen im `OVRPlugin` erkannt wurden. Hierzu müssen Sie den Editor lediglich neu starten. Nach dem Neustart können drei neue Fehlermeldungen auftreten:
> `[Package Manager Window] Error while getting auth code: User is not logged in or user status invalid. Unity.Editor.EditorApplication:Internal_CallUpdateFunctions ()`

Starten Sie Unity in diesem Fall einfach erneut; danach sollten die Fehlermeldungen verschwunden sein. Alternativ finden Sie [hier im Unity-Forum](https://forum.unity.com/threads/package-manager-window-unable-to-perform-online-search.1136377/) Lösungsvorschläge.

Alle verbleibenden Meldungen in der Konsole des Unity Editors können Sie bedenkenlos löschen. Sie haben keine Auswirkungen auf unsere Applikation!

---

## Gameplay

Das Gameplay wurde durch die Funktionalitäten eines Segways inspiriert.

**Fortbewegung:**
* **Nach vorn:** Lehnen nach vorn
* **Nach hinten:** Lehnen nach hinten
* **Drehung nach rechts:** Controller (evtl. mit physischer Stange) entlang der positiven X-Achse bewegen
* **Drehung nach links:** Controller (evtl. mit physischer Stange) entlang der negativen X-Achse bewegen

**Interaktionen:**
* **Artikel einsammeln:** Mit den Händen kann direkt mit den Artikeln interagiert werden.
* **Hupen:** Den `PrimaryHandTrigger` oder `SecondaryHandTrigger` drücken.
* **Liste de- oder aktivieren:** Den `PrimaryIndexTrigger` oder `SecondaryIndexTrigger` drücken.

---

## Assets

**SDKs:**
* [Meta XR Core SDK](https://assetstore.unity.com/packages/tools/integration/meta-xr-core-sdk-269169)
* [Meta Interaction OVR Integration SDK](https://assetstore.unity.com/packages/tools/integration/meta-xr-interaction-sdk-ovr-integration-265014) *(Hinweis: Wir haben hier das OVRCameraRigInteraction verwendet, aber alle bereits implementierten Interaktionen gelöscht. Dabei wird auch das Meta XR Interaction SDK installiert.)*
* Oculus XR Plugin

**Text:**
* TextMesh Pro

**Musik und Sound:**
* [Hintergrundmusik (Wii Shop)](https://www.101soundboards.com/sounds/24303004-wii-shop)
* [Hupe](https://www.101soundboards.com/sounds/27481824-horn-honk-short)

**Kaufhaus-Modelle:**
* [Uhr](https://assetstore.unity.com/packages/3d/props/interior/clock-free-44164)
* [Brunnen](https://sketchfab.com/3d-models/fountain-1e2234e51a46400bbd3a71afd9c2b750#download)
* [Bank](https://assetstore.unity.com/packages/3d/environments/modern-bench-pack-221011)
* [Rahmen für die Poster](https://sketchfab.com/3d-models/poster-frame-fb500d75d785433c8b82fdafac9e18cb)
* [Pothos Pflanzen](https://sketchfab.com/3d-models/free-pothos-potted-plant-money-plant-e9832f38484f4f85b3f9081b51fa3799)
* [WC Türen](https://assetstore.unity.com/packages/3d/props/interior/door-free-pack-aferar-148411)
* [Läden](https://sketchfab.com/3d-models/sketchfab-store-in-mall-957c1d65e6db4598a198f7ac3888fed1)

**Bilder für die Poster:**
* [Deutsche Nationalmannschaft](https://www.ferrero-sammelspass.de/img/shop/Album/998-album.jpg?version=9)
* [Der Kaufhaus Cop](https://image.tmdb.org/t/p/original/5o8kxVsJKw9bdxtsIreBNHSClID.jpg)
* [konzenTRiert (Uni Trier)](https://www.uni-trier.de/fileadmin/_processed_/1/5/csm_Titelseite_konzenTRiert2021_b65cd70fe6.jpg)
* [Trier](https://www.lieferlokal.de/sites/default/files/styles/1700x2424/public/tr-produktmood-00.jpg?itok=w6Smw1I6)
* [Tabletten](https://www.adworld.ie/wp-content/uploads/2016/09/op.jpg)
* [Seven-Up](https://grist.org/wp-content/uploads/2010/07/ad_7up175baby.jpg)
* [Mario](https://mir-s3-cdn-cf.behance.net/project_modules/max_1200/64f85628578453.55c7bc0a8498b.jpg)
* *Hinweis:* Angry Birds von der zweiten Übung und den Ames Room von der ersten Übung haben wir selbst erstellt.