# LF3 - LS 3.1: BYOD im WLAN
## Antworten zum Text „Funkübersicht" (c't, 2015, Heft 15)

---

## Antwort 1: Bruttorate vs. Nettorate

**Warum kommt von der Bruttorate auf Anwendungsebene stets deutlich weniger an?**

Die Bruttodatenrate gibt die theoretisch maximal mögliche Übertragungsgeschwindigkeit an. Auf Anwendungsebene kommt jedoch deutlich weniger an, weil:

1. **Zugriffsprotokoll mit Sendepausen:** Wenn ein WLAN-Teilnehmer sendet, müssen die anderen auf dem Funkkanal schweigen, damit die Daten ungestört ankommen. Alle Geräte in Reichweite teilen sich das Medium Funk.

2. **Protokoll-Overhead:**
   - Management-Frames (Beacons, Acknowledgements)
   - Header-Informationen in jedem Datenpaket
   - Fehlerkorrektur und Prüfsummen

3. **Wartezeiten (CSMA/CA):**
   - Carrier Sense Multiple Access with Collision Avoidance
   - Geräte müssen auf freien Kanal warten
   - Zufällige Backoff-Zeiten nach Kollisionen

4. **Verschlüsselung:** Zusätzlicher Overhead durch WPA2/WPA3

5. **Signalqualität:** Bei schlechterem SNR (Signal to Noise Ratio) wird auf robustere, aber langsamere Modulationsarten zurückgeschaltet

**Typischer Netto-Durchsatz:** Ca. 50-70% der Bruttorate im optimalen Fall

---

## Antwort 2: WLAN-Standards und Frequenzbänder

**Welche WLAN-Standards nutzen welche Frequenzbänder?**

| Standard | Erscheinungsjahr | Frequenzband | Max. Bruttorate |
|----------|------------------|--------------|-----------------|
| **802.11** | 1997 | 2,4 GHz | 2 MBit/s |
| **802.11b** | 1999 | 2,4 GHz | 11 MBit/s |
| **802.11a** | 1999 | 5 GHz | 54 MBit/s |
| **802.11g** | 2002 | 2,4 GHz | 54 MBit/s |
| **802.11n** | 2006 | 2,4 GHz und 5 GHz | 600 MBit/s |
| **802.11ac** | 2012 | 5 GHz | 6933 MBit/s |
| **802.11ad** | 2012 | 60 GHz | 6757 MBit/s |
| **802.11ax (WiFi 6)** | 2019 | 2,4 GHz und 5 GHz | 9608 MBit/s |
| **802.11be (WiFi 7)** | 2024 | 2,4, 5 und 6 GHz | 46 Gbit/s |

**Wie ist das entstanden?**

- **1997 - Ursprung:** WLAN startete im 2,4-GHz-Band, da dies ein lizenzfreies ISM-Band ist
- **1999 - Erste Erweiterung:** 802.11a erschien für das 5-GHz-Band, um höhere Geschwindigkeiten und eine Ausweichspur zu bieten
- **2006 - Flexibilität:** 802.11n führte Dualband-Betrieb ein (2,4 und 5 GHz)
- **2012 - Spezialisierung:** 802.11ac nutzt nur 5 GHz für maximale Geschwindigkeit
- **2012 - Kurzstrecke:** 802.11ad erschloss das 60-GHz-Band für sehr hohe Geschwindigkeiten auf kurze Distanz
- **Ab 2010:** Simultan-Dualband-Router wurden verbreitet, da 11n etablierte sich
- **Heute:** Moderne Standards wie WiFi 6/6E/7 nutzen mehrere Bänder gleichzeitig

---

## Antwort 3: Kanäle in den Frequenzbändern

**Wie viele Kanäle werden in den Frequenzbändern angeboten?**

### 2,4-GHz-Band (2,400 - 2,485 GHz)

**Kanäle:** 13 Kanäle (in Europa), jeder 20 MHz breit
- Kanal 1: 2,412 GHz
- Kanal 6: 2,437 GHz
- Kanal 11: 2,462 GHz
- Kanal 13: 2,472 GHz

**Eigenschaften:**
- **Überlappung:** Kanäle überlappen sich
- **Überlappungsfrei:** Nur 3 Kanäle können gleichzeitig störungsfrei genutzt werden (Kanäle 1, 6, 11)
- **Problem:** In Städten stark überlaufen
- **Störungen:** Bluetooth, Mikrowellen, andere Funkgeräte
- **Reichweite:** Größere Reichweite, bessere Wanddurchdringung

### 5-GHz-Band (5,15 - 5,725 GHz in Europa)

**Kanäle:** Viel mehr Kanäle verfügbar
- Kanal 36-48: Ohne DFS/TPC nutzbar
- Kanal 52-140: Mit DFS/TPC nutzbar (Radar-Erkennung erforderlich)
- Kanal 149-165: In Europa nicht erlaubt, nur in USA/Asien

**Eigenschaften:**
- **20 MHz breit:** Viele parallele Kanäle möglich
- **Weniger überlaufen:** In Städten deutlich freier
- **Keine Überlappung:** Kanäle überlappen sich nicht
- **Reichweite:** Geringere Reichweite, schlechtere Wanddurchdringung
- **Höhere Geschwindigkeit:** Unterstützt moderne Standards wie 11ac

**Übersicht bei 11a (20 MHz):**
- 4 Kanäle (36, 40, 44, 48) ohne DFS/TPC
- Bis zu 19 Kanäle mit DFS/TPC in Europa

---

## Antwort 4: Dual-Band

**Was ist Dual-Band?**

**Definition:** Fähigkeit von WLAN-Geräten, in beiden Frequenzbändern (2,4 GHz und 5 GHz) zu arbeiten.

**Zwei Arten:**

### 1. Einfaches Dualband
- Gerät kann entweder auf 2,4 GHz ODER auf 5 GHz arbeiten
- Umschalten zwischen den Bändern möglich
- Nicht gleichzeitig

### 2. Simultan-Dualband (Concurrent Dualband)
- Router/AP kann in beiden Bändern **gleichzeitig** arbeiten
- Benötigt zwei separate Funkmodule
- Bei 11ac ist Simultan-Dualband Pflicht, da:
  - 11ac nur für 5 GHz definiert ist
  - Ältere 2,4-GHz-Clients parallel per 11n bedient werden müssen

**Vorteile:**
- Ausweichen auf weniger überlaufenes 5-GHz-Band möglich
- Höhere Gesamtkapazität
- Flexibilität: Schnelle Geräte auf 5 GHz, ältere auf 2,4 GHz
- Bessere Performance bei vielen Clients

**Client-Seite:**
- Dualband-Clients können das weniger gestörte Band wählen
- Automatische Bandsteuerung (Band Steering) möglich

---

## Antwort 5: Kanalbreite (Spurbreite)

**Wie breit können die „Spuren" sein?**

### 2,4-GHz-Band
- **11n+g:** 20 MHz (Standardbreite)
- **11n:** 40 MHz (Kanalbündelung möglich)

**Problem bei 40 MHz:**
- Ohne DFS/TPC nur 2 unabhängige 40-MHz-Spuren möglich (36+40 sowie 44+48)
- Starke Überlappung mit Nachbar-WLANs
- In Mehrfamilienhäusern nicht empfohlen

### 5-GHz-Band
- **11a:** 20 MHz
- **11n:** 20 MHz oder 40 MHz
- **11ac:** 20, 40, 80 oder 160 MHz
- **11ax/be:** Bis zu 320 MHz

**Eigenschaften:**

| Kanalbreite | Vorteile | Nachteile |
|-------------|----------|-----------|
| **20 MHz** | - Viele parallele Kanäle<br>- Weniger Störungen<br>- Besser bei hoher WLAN-Dichte | - Niedrigere Geschwindigkeit |
| **40 MHz** | - Ca. doppelte Geschwindigkeit<br>- Guter Kompromiss | - Weniger Kanäle verfügbar<br>- Mehr Störpotential |
| **80 MHz** | - Sehr hohe Geschwindigkeit<br>- Volle 11ac-Performance | - Nur mit DFS/TPC im 5-GHz-Band<br>- Wenige Kanäle<br>- Hohe Störanfälligkeit |
| **160 MHz** | - Maximale Geschwindigkeit | - Sehr wenige Kanäle<br>- Nur in wenigen Szenarien sinnvoll<br>- Hohe Interferenz |

**Faustregeln:**
- **Verdoppelung der Kanalbreite** → ca. **doppelte Geschwindigkeit**
- **In Städten/Mehrfamilienhäusern:** 20 oder 40 MHz empfohlen
- **Freie Umgebung:** 80 oder 160 MHz möglich
- **11ac mit 80 MHz:** Alle Nachbarn müssen sich auf denselben Kanalblock drängeln (36+40+44+48)

---

## Antwort 6: DFS (Dynamic Frequency Selection)

**Welchen Zweck verfolgt DFS?**

**DFS = Dynamic Frequency Selection**

**Zweck:**
1. **Radar-Erkennung:** Erkennt Signale von (Wetter-)Radarsystemen im 5-GHz-Band
2. **Automatischer Kanalwechsel:** Wechselt automatisch den Kanal, wenn Radar erkannt wird
3. **Regulatorische Anforderung:** Erfüllt gesetzliche Vorgaben zur Nutzung des 5-GHz-Bands

**Hintergrund:**
- Das 5-GHz-Band wird auch von Wetterradaren, militärischen Radarsystemen und Flugsicherung genutzt
- Diese haben Vorrang und dürfen nicht gestört werden
- WLAN-Geräte müssen bei Radar-Erkennung sofort auf einen anderen Kanal wechseln

**Auswirkung:**
- **Mit DFS/TPC:** Zugang zu Kanälen 36-140 (voller Zugriff auf 5-GHz-Band)
- **Ohne DFS/TPC:** Nur Kanäle 36-48 in Europa nutzbar
- **Wichtig für 11ac:** Bei 80-MHz-Kanälen nur ein Block verfügbar ohne DFS

**Problem:**
Längst nicht jeder Hersteller implementiert DFS/TPC korrekt, was die Nutzung des 5-GHz-Bands stark einschränkt.

**Empfehlung:**
Beim Kauf darauf achten, dass Geräte DFS unterstützen!

---

## Antwort 7: TPC (Transmit Power Control)

**Welche Bedeutung hat TPC?**

**TPC = Transmit Power Control**

**Bedeutung:**
1. **Automatisches Absenken der Sendeleistung** bei guten Verbindungen
2. **Optimierung:** So weit reduzieren, dass die Datenrate gerade nicht zurückgeht
3. **Ressourcenschonung:** Geringerer Stromverbrauch
4. **Störungsreduktion:** Weniger Interferenzen mit Nachbar-WLANs

**Zweck im 5-GHz-Band:**
- **Regulatorische Anforderung:** Zusammen mit DFS erforderlich, um das gesamte 5-GHz-Band nutzen zu dürfen
- **Effizienz:** Vermeidet unnötig hohe Sendeleistung
- **Koexistenz:** Verbessert das Zusammenleben mehrerer WLANs

**Funktionsweise:**
- Misst die Verbindungsqualität (SNR, Signalstärke)
- Passt Sendeleistung dynamisch an
- Bei guter Verbindung: Sendeleistung runter
- Bei schlechter Verbindung: Sendeleistung hoch

**Vorteile:**
- Längere Akkulaufzeit bei mobilen Geräten
- Geringere HF-Belastung
- Bessere Spektrumseffizienz
- Weniger Störungen in dicht besiedelten Bereichen

**Zusammenhang mit DFS:**
Ohne DFS **und** TPC dürfen WLAN-Basen in Europa im 5-GHz-Band nur auf Kanälen 36-48 arbeiten.

---

## Antwort 8: MIMO

**Was ist MIMO und was bewirkt es?**

**MIMO = Multiple Input Multiple Output**

**Definition:**
Übertragungstechnik, bei der mehrere Datenströme gleichzeitig auf derselben Frequenz über mehrere Antennen übertragen werden.

**Funktionsweise:**
- **Multiple Input:** Mehrere Sendeantennen
- **Multiple Output:** Mehrere Empfangsantennen
- **Gleichzeitige Übertragung:** Verschiedene Datenströme parallel
- **Räumliche Trennung:** Nutzt Mehrwegeausbreitung des Funksignals

**Geschichte:**
- **Anno 2005:** Erste WLAN-Basen mit MIMO erschienen
- **Vorher unmöglich gehalten:** Mehrere Datenströme gleichzeitig auf derselben Frequenz

**Bewirkung:**

1. **Höhere Geschwindigkeit:**
   - 1 Stream (SISO): Bis zu 433 MBit/s bei 11ac
   - 2 Streams: Bis zu 867 MBit/s
   - 3 Streams: Bis zu 1300 MBit/s
   - 4 Streams: Bis zu 1733 MBit/s

2. **Bessere Zuverlässigkeit:**
   - Redundanz durch mehrere Signalwege
   - Weniger anfällig für Störungen
   - Stützsignale verbessern Verbindung

3. **Größere Reichweite:**
   - Bessere Signalqualität
   - Robustere Verbindung

**MIMO-Streams in Standards:**
- **802.11n:** Bis zu 4 Streams
- **802.11ac:** Bis zu 8 Streams
- **Praktisch:** Router meist 2-4 Streams, Clients 1-2 Streams

**Beispiel:**
Router mit 3 Antennen + Client mit 2 Antennen = 2 Streams genutzt, dritte Antenne liefert Stützsignal (+20% Durchsatz)

---

## Antwort 9: Antennenanzahl

**Welche Bedeutung hat die Anzahl der Antennen?**

**Bedeutung:**

1. **Anzahl der MIMO-Streams:**
   - 1 Antenne = 1 Stream
   - 2 Antennen = 2 Streams
   - 3 Antennen = 3 Streams
   - 4+ Antennen = 4+ Streams

2. **Maximale Geschwindigkeit** (bei 11ac, 80 MHz, 5 GHz):
   - 1 Antenne: 433 MBit/s brutto
   - 2 Antennen: 867 MBit/s brutto
   - 3 Antennen: 1300 MBit/s brutto
   - 4 Antennen: 1733 MBit/s brutto

3. **Asymmetrische Konfigurationen:**
   - Router: 3 Antennen, Client: 2 Antennen → 2 Streams aktiv
   - Dritte Router-Antenne: Stützsignal (+20% Durchsatz)

4. **Sichtbarkeit:**
   - Antennen sind nicht immer von außen sichtbar
   - Oft intern verbaut (besonders bei Clients)
   - Information steht im Kleingedruckten

**Typische Konfigurationen:**

| Gerätetyp | Typische Antennenanzahl |
|-----------|-------------------------|
| **Smartphone** | 1 Antenne (manchmal 2) |
| **Tablet** | 1-2 Antennen |
| **Billig-Notebook** | 1 Antenne |
| **Standard-Notebook** | 2 Antennen |
| **Premium-Notebook** | 3 Antennen (z.B. MacBook Pro) |
| **WLAN-Router (günstig)** | 2 Antennen |
| **WLAN-Router (Standard)** | 3 Antennen |
| **WLAN-Router (High-End)** | 4+ Antennen |

**Beispiele für Smartphones:**
- **iPhone 14/15:** 2x2 MIMO (2 Antennen)
- **Samsung Galaxy S23:** 2x2 MIMO (2 Antennen)
- **Ältere/Budget-Smartphones:** Oft nur 1 Antenne

**Wichtig:**
Die Gesamtgeschwindigkeit wird durch das Gerät mit den wenigsten Antennen begrenzt!

**Wie viele Antennen hat Ihr Smartphone?**
*Diese Frage ist individuell zu beantworten. Typischerweise haben moderne Smartphones 1-2 WLAN-Antennen. Die genaue Anzahl findet man in den technischen Spezifikationen des Herstellers.*

---

## Antwort 10: Parameter der Bruttodatenrate

**Weitere Parameter, die Einfluss auf die Bruttodatenrate haben:**

### 1. Modulationsart
- **1, 2, 4, 6, 8, 10 Bit pro Symbol**
- Abhängig von Signalqualität (SNR)
- Höhere Modulation = mehr Daten, aber anfälliger für Störungen
- Beispiele:
  - BPSK: 1 Bit/Symbol
  - QPSK: 2 Bit/Symbol
  - 16-QAM: 4 Bit/Symbol
  - 64-QAM: 6 Bit/Symbol
  - 256-QAM: 8 Bit/Symbol
  - 1024-QAM: 10 Bit/Symbol (proprietär, z.B. NitroQAM)

### 2. Kanalbreite
- **20, 40, 80, 160 MHz**
- Verdoppelung ≈ doppelte Geschwindigkeit
- Größere Breite = mehr Störanfälligkeit

### 3. Anzahl der MIMO-Streams
- **1 bis 8 Streams** (je nach Standard und Hardware)
- Mehr Streams = höhere Geschwindigkeit
- Begrenzt durch Gerät mit wenigsten Antennen

### 4. Guard Interval (GI)
- **Schutzintervall zwischen Datenpaketen**
- Standard: 800 ns (Long GI)
- Kurz: 400 ns (Short GI) bei 11n/ac
- Sehr kurz: 800/1600/3200 ns bei 11ax
- Short GI: +11% Durchsatz, aber anfälliger für Mehrwegeausbreitung

### 5. WLAN-Standard
- 802.11b, g, a, n, ac, ax, be
- Neuere Standards effizienter und schneller

### 6. Frequenzband
- 2,4 GHz: Niedriger, aber störanfälliger
- 5 GHz: Höher, aber kürzere Reichweite
- 6 GHz (WiFi 6E/7): Noch mehr Kapazität

### 7. Signalqualität (SNR - Signal to Noise Ratio)
- Verhältnis Signal zu Rauschen
- Niedriges SNR → robustere, langsamere Modulation
- Hohes SNR → schnellere Modulation möglich

### 8. Coding Rate
- Verhältnis Nutzdaten zu Fehlerkorrektur
- 1/2, 2/3, 3/4, 5/6 (mehr Fehlerkorrektur bei schlechter Verbindung)

### 9. OFDM-Subcarrier
- Anzahl der Unterträger
- 11ac: 234 bei 80 MHz
- 11ax: 980 bei 80 MHz (effizientere Nutzung)

### 10. Beamforming
- Gezielte Ausrichtung des Signals
- Verbessert SNR beim Empfänger
- Ermöglicht höhere Modulationsarten

### 11. Spatial Streams vs. Space-Time Streams
- Bei 11ax: Mehr Effizienz durch bessere Codierung

### 12. MCS (Modulation and Coding Scheme) Index
- Kombiniert Modulation und Coding Rate
- MCS 0-11 (11ac/ax)
- Höherer MCS = höhere Datenrate

**Zusammenspiel:**
All diese Parameter werden dynamisch angepasst, um die beste Balance zwischen Geschwindigkeit und Zuverlässigkeit zu erreichen.

---

## Antwort 11: SISO, Diversity und MU-MIMO

### SISO (Single Input Single Output)

**Definition:** Klassische Funkübertragungstechnik

**Funktionsweise:**
- Ein Signal wird über eine Antenne gesendet (Single Input in den Funkkanal)
- Auf der anderen Seite wird es mit einer Antenne empfangen (Single Output)
- Ein Datenstrom zur Zeit

**Eigenschaften:**
- Einfachste WLAN-Form
- Verwendet bei frühen Standards (802.11, 11b, 11a, 11g)
- Begrenzte Geschwindigkeit
- Anfällig für Störungen durch Mehrwegeausbreitung

**Geschwindigkeit:**
- 802.11b: Max. 11 MBit/s
- 802.11a/g: Max. 54 MBit/s
- 11ac (1 Stream): Max. 433 MBit/s

---

### Diversity

**Definition:** Technik zur Verbesserung der Signalqualität durch Antennenwahl

**Funktionsweise:**
- Gerät hat mehrere Antennen (typisch 2)
- **Nur eine Antenne** wird zu einem Zeitpunkt genutzt
- Dynamische Wahl der aktuell besseren Antenne
- Umschaltung je nach Empfangsqualität

**Arten:**
1. **Receive Diversity:** Wahl der besten Empfangsantenne
2. **Transmit Diversity:** Wahl der besten Sendeantenne
3. **Selection Diversity:** Auswahl basierend auf Signal-Stärke

**Vorteile:**
- Bessere Verbindungsstabilität
- Höhere Reichweite
- Weniger Verbindungsabbrüche
- Keine höhere Geschwindigkeit (nur Stabilität!)

**Unterschied zu MIMO:**
- Diversity: Nur eine Antenne aktiv → **ein** Datenstrom
- MIMO: Mehrere Antennen aktiv → **mehrere** Datenströme parallel

---

### MU-MIMO (Multi-User MIMO)

**Definition:** Weiterentwicklung von MIMO, die es erlaubt, mehrere Clients gleichzeitig zu bedienen

**MU-MIMO = Multi-User Multiple Input Multiple Output**

**Funktionsweise:**
- Access Point sendet Daten **gleichzeitig** an mehrere Clients
- Statt nacheinander werden 2-4 Clients parallel bedient
- Nutzt verschiedene räumliche Richtungen (Beamforming)

**Beispiel:**

**Ohne MU-MIMO (herkömmlich):**
- Router (3 Antennen) sendet nacheinander:
  - Client 1 (1 Antenne): 433 MBit/s → wartet
  - Client 2 (1 Antenne): 433 MBit/s → wartet
  - Client 3 (1 Antenne): 433 MBit/s → wartet
- 1300 MBit/s des Routers weitgehend ungenutzt

**Mit MU-MIMO:**
- Router sendet gleichzeitig:
  - Client 1: 433 MBit/s
  - Client 2: 433 MBit/s
  - Client 3: 433 MBit/s
- Alle drei Streams parallel = volle Kapazität genutzt

**Vorteile:**
1. **Höhere Gesamteffizienz:** Funkkanal schneller wieder frei
2. **Bessere Performance:** Bei mehreren aktiven Clients
3. **Geringere Latenz:** Weniger Wartezeit für Clients
4. **Bessere Ausnutzung:** Router-Kapazität wird voll genutzt

**Einschränkungen:**
- Funktioniert nur im **Downlink** (Router → Client)
- Bei 11ac: Noch nicht für Uplink (Client → Router)
- Bei 11ax (WiFi 6): Auch Uplink MU-MIMO möglich
- **Beide Seiten müssen MU-MIMO unterstützen**
- Nicht alle Geräte sind kompatibel

**Stand 2015:**
- Erste MU-MIMO-Router kommen auf den Markt
- Kaum Clients verfügbar
- Noch Kinderkrankheiten zu erwarten
- Keine Eile beim Kauf empfohlen

**Typische Konfiguration:**
- Router: 4 Antennen für MU-MIMO
- Kann z.B. 2×2-Stream-Clients oder 4×1-Stream-Clients gleichzeitig bedienen

**Zukunft:**
- WiFi 6 (11ax): MU-MIMO bidirektional
- WiFi 7 (11be): Noch mehr gleichzeitige Clients

---

## Antwort 12: Repeater

**Was macht ein Repeater?**

**Definition:**
Ein Repeater verlängert die Reichweite eines WLANs, indem er das Signal empfängt und erneut aussendet.

**Funktionsweise:**
1. **Client-Funktion:** Nimmt als Client Kontakt zum Router auf
2. **Access-Point-Funktion:** Stellt die Verbindung wiederum als AP zur Verfügung
3. **Brückenfunktion:** Verbindet zwei Bereiche, die sonst keine direkte Funkverbindung hätten

**Platzierung:**
- **Optimal:** Auf halber Strecke zwischen Router und Funkloch
- Gute Verbindung zum Router erforderlich
- Gute Verbindung zu den Clients erforderlich

**Zusatzfunktion:**
- Verbindung kann oft auch an LAN-Ports zur Verfügung stehen
- Verkabelte Geräte können so angeschlossen werden

---

### Repeater-Typen

#### 1. Single-Band-Repeater

**Eigenschaften:**
- Arbeitet nur auf einem Frequenzband (meist 2,4 GHz)
- Sendet und empfängt auf demselben Kanal

**Funktionsweise:**
- Empfängt Daten vom Router auf 2,4 GHz
- Sendet sie wieder auf 2,4 GHz an Clients

**Vorteile:**
- Günstig (Aktionsware ab unter 20 Euro)
- Einfache Einrichtung
- Grundversorgung ausreichend

**Nachteile:**
- **Halbiert den Durchsatz:** Jedes Datenpaket belegt den Funkkanal zweimal
  1. Router → Repeater
  2. Repeater → Client
- Langsame Performance bei hoher Last
- Erhöht Latenz

**Typische Geschwindigkeit:**
- Router-Repeater: 150 MBit/s (11n)
- Repeater-Client: Nochmal die gleichen Daten senden
- **Effektiv:** Ca. 50-70 MBit/s Netto beim Client

---

#### 2. Crossband-Repeater (Dualband-Repeater)

**Eigenschaften:**
- Arbeitet in beiden Frequenzbändern gleichzeitig
- Nutzt 2,4 GHz und 5 GHz parallel

**Funktionsweise:**
- Empfängt Daten vom Router auf einem Band (z.B. 5 GHz)
- Sendet sie auf dem anderen Band weiter (z.B. 2,4 GHz)
- Oder umgekehrt

**Beispiel:**
- Client verbindet sich auf 2,4 GHz mit Repeater
- Repeater schickt Daten im 5-GHz-Band weiter zum Router
- Jedes Band wird nur einmal genutzt

**Vorteile:**
- **Kein Durchsatzverlust durch Wiederholung:** Datenpaket belegt nicht zweimal denselben Kanal
- Deutlich schneller als Single-Band
- Gesamter Transfer läuft flotter
- Vermeidet Wartezeiten im WLAN-Protokoll

**Nachteile:**
- Teurer als Single-Band-Repeater
- Benötigt Simultan-Dualband-Router
- Beide Frequenzbänder müssen gut empfangbar sein

**Voraussetzungen:**
- Router muss Simultan-Dualband unterstützen
- Dualband-fähige Clients profitieren am meisten

**Typische Geschwindigkeit:**
- Router-Repeater: 867 MBit/s auf 5 GHz
- Repeater-Client: 300 MBit/s auf 2,4 GHz
- **Effektiv:** Ca. 150-200 MBit/s Netto beim Client (deutlich besser als Single-Band)

---

#### 3. Mesh-Repeater (Moderne Lösung)

**Eigenschaften:**
- Teil eines Mesh-Netzwerks
- Intelligente Weiterleitung
- Mehrere Access Points arbeiten zusammen

**Vorteile:**
- Automatisches Roaming zwischen APs
- Selbstheilend bei Ausfall eines Knotens
- Zentrale Verwaltung
- Optimale Routenwahl

**Nachteile:**
- Teurer
- Oft herstellergebunden
- Komplexere Einrichtung

---

### Vergleich der Repeater-Typen

| Typ | Preis | Durchsatz | Komplexität | Empfehlung |
|-----|-------|-----------|-------------|------------|
| **Single-Band** | € | ⭐⭐ | Einfach | Grundversorgung, wenig Traffic |
| **Crossband** | €€€ | ⭐⭐⭐⭐ | Mittel | Höhere Ansprüche, Backups, Streaming |
| **Mesh** | €€€€ | ⭐⭐⭐⭐⭐ | Mittel-Hoch | Große Flächen, viele Clients, Premium |

---

## Antwort 13: WLAN-Verschlüsselung

**Was bewirken WEP, WPA1 bis WPA3?**

### WEP (Wired Equivalent Privacy)

**Erschienen:** 1997

**Eigenschaften:**
- Erste WLAN-Verschlüsselung
- Sollte Sicherheit wie bei Kabelnetzen bieten

**Verschlüsselung:**
- RC4-Stream-Cipher
- 64-Bit oder 128-Bit Schlüssel
- Statischer Schlüssel

**Status:** ⚠️ **VERALTET UND GEBROCHEN**

**Sicherheit:**
- Bereits 2001 geknackt
- In wenigen Minuten zu brechen
- Bietet praktisch keinen Schutz mehr

**Empfehlung:** ❌ **KEINESFALLS VERWENDEN!**

---

### WPA (Wi-Fi Protected Access) / WPA1

**Erschienen:** 2003

**Hintergrund:**
- Schnelle Reaktion auf WEP-Schwachstellen
- Zwischenlösung bis WPA2 fertig war

**Verschlüsselung:**
- **TKIP (Temporal Key Integrity Protocol)**
- Dynamische Schlüssel
- Verbesserter Integritätsschutz (MIC - Message Integrity Check)

**Verbesserungen gegenüber WEP:**
- Schlüssel wechseln regelmäßig
- Besserer Schutz gegen Replay-Attacks
- Erheblich sicherer als WEP

**Status:** ⚠️ **VERALTET**

**Sicherheit:**
- Deutlich sicherer als WEP
- Aber mittlerweile auch angreifbar
- Zwingt schnelle WLAN-Geräte auf langsame Datenraten

**Empfehlung:** ⚠️ **Nicht mehr verwenden, zu WPA2/WPA3 wechseln**

---

### WPA2 (Wi-Fi Protected Access 2)

**Erschienen:** 2004

**Standard:** Basiert auf IEEE 802.11i

**Verschlüsselung:**
- **AES (Advanced Encryption Standard)**
- CCMP (Counter Mode with CBC-MAC Protocol)
- 128-Bit Verschlüsselung (oder höher)

**Verbesserungen gegenüber WPA:**
- Viel stärkere Verschlüsselung (AES statt RC4)
- Bessere Authentifizierung
- Robusterer Integritätsschutz

**Status:** ✅ **AKTUELLER STANDARD (seit 2004)**

**Sicherheit:**
- Für den Heimgebrauch ausreichend sicher
- **Voraussetzung:** Starkes Passwort erforderlich!
- Anfällig für Brute-Force bei schwachen Passwörtern

**Schwachstellen:**
- **KRACK-Angriff (2017):** Ausnutzung des 4-Way-Handshakes
- Angreifer kann Verbindungsaufbau mitschneiden
- Schwache Passwörter können offline geknackt werden
- Nachträgliche Entschlüsselung aufgezeichneten Verkehrs möglich

**Empfehlung:** ✅ **Verwenden mit starkem Passwort (min. 12-20 Zeichen)**

---

### WPA3 (Wi-Fi Protected Access 3)

**Erschienen:** 2018/2019

**Verbesserungen gegenüber WPA2:**

1. **SAE (Simultaneous Authentication of Equals) / Dragonfly-Handshake:**
   - Ersetzt anfälligen 4-Way-Handshake
   - Schutz gegen Offline-Wörterbuch-Attacken
   - Forward Secrecy

2. **Individualized Data Encryption:**
   - Jede Verbindung eigener Verschlüsselungsschlüssel
   - Auch in offenen Netzen

3. **192-Bit Verschlüsselung (WPA3-Enterprise):**
   - Noch stärkere Verschlüsselung
   - Für höchste Sicherheitsanforderungen

4. **Schutz gegen Brute-Force:**
   - Auch schwächere Passwörter besser geschützt
   - Angreifer kann Mitschnitt nicht offline angreifen

5. **Easy Connect:**
   - Vereinfachtes Hinzufügen von Geräten ohne Display
   - QR-Code-basiert

**Status:** ✅ **NEUESTER STANDARD**

**Verfügbarkeit (2015-2024):**
- 2015: Noch nicht verfügbar (erst 2018 spezifiziert)
- Ab 2019: Erste WPA3-Geräte
- 2024: Weitgehend verfügbar, aber noch nicht überall Standard

**Empfehlung:** ✅ **Verwenden, wenn verfügbar**

---

### WPA-Personal vs. WPA-Enterprise

#### WPA-Personal (WPA-PSK = Pre-Shared Key)

**Für:** Privatanwender, kleine Büros, Heimnetze

**Authentifizierung:**
- Ein gemeinsames Passwort (PSK) für alle Benutzer
- Passwort wird auf dem Router/AP konfiguriert
- Jeder kennt dasselbe Passwort

**Vorteile:**
- Einfache Einrichtung
- Keine zusätzliche Infrastruktur nötig
- Für Heimanwendung ausreichend

**Nachteile:**
- Alle teilen sich ein Passwort
- Bei Passwort-Wechsel müssen alle Geräte neu konfiguriert werden
- Kein individuelles Tracking von Benutzern
- Ausgetretene Mitarbeiter: Passwort muss geändert werden

**Varianten:**
- WPA2-Personal (mit AES)
- WPA3-Personal (mit SAE)

---

#### WPA-Enterprise (WPA-802.1X / WPA-RADIUS)

**Für:** Unternehmen, Universitäten, große Organisationen

**Authentifizierung:**
- **Individuelle Zugangsdaten** für jeden Benutzer
- Zentraler Authentifizierungsserver (RADIUS-Server)
- Verschiedene Methoden:
  - Benutzername + Passwort
  - Digitale Zertifikate
  - Smartcards
  - Multi-Faktor-Authentifizierung

**Komponenten:**
1. **Client (Supplicant):** Gerät, das sich anmelden will
2. **Authenticator (AP):** Access Point
3. **Authentication Server:** RADIUS-Server (z.B. FreeRADIUS, Windows NPS)

**Protokoll:** IEEE 802.1X

**EAP-Methoden (Extensible Authentication Protocol):**
- **EAP-TLS:** Zertifikat-basiert, sehr sicher
- **EAP-TTLS:** Tunnel-basiert mit Zertifikat
- **EAP-PEAP:** Protected EAP, weit verbreitet
- **EAP-MSCHAPv2:** Microsoft-Standard
- **EAP-SIM:** Für Mobilfunk-basierte Auth

**Vorteile:**
1. **Individuelle Zugangsdaten:** Jeder Benutzer hat eigene Credentials
2. **Zentrale Verwaltung:** User-Verwaltung über RADIUS
3. **Audit-Trail:** Nachvollziehbar, wer wann im Netz war
4. **Dynamische Schlüssel:** Jede Session eigener Schlüssel
5. **Einfaches Onboarding/Offboarding:** User zentral aktivieren/deaktivieren
6. **Höhere Sicherheit:** Zertifikat-basierte Auth möglich
7. **Integration:** Anbindung an Active Directory, LDAP möglich

**Nachteile:**
- Komplexere Einrichtung
- RADIUS-Server erforderlich (zusätzliche Infrastruktur)
- Höherer Verwaltungsaufwand
- Nicht für Heimanwender geeignet

**Varianten:**
- WPA2-Enterprise (mit AES + RADIUS)
- WPA3-Enterprise (mit 192-Bit + RADIUS)

---

### Zusammenfassung: Empfehlungen

| Verschlüsselung | Status | Empfehlung | Anwendungsfall |
|-----------------|--------|------------|----------------|
| **Offen (keine)** | ❌ | Nie verwenden | - |
| **WEP** | ❌ | Nie verwenden | - |
| **WPA/TKIP** | ⚠️ | Veraltet | - |
| **WPA2-Personal** | ✅ | Aktuell empfohlen | Heimnetze mit starkem Passwort |
| **WPA3-Personal** | ✅✅ | Beste Wahl | Heimnetze (wenn verfügbar) |
| **WPA2-Enterprise** | ✅ | Für Firmen | Unternehmen, Universitäten |
| **WPA3-Enterprise** | ✅✅ | Beste Wahl Firmen | Unternehmen mit höchsten Anforderungen |

**Passwort-Empfehlungen (für Personal):**
- Mindestens 12-20 Zeichen
- Kombination: Groß-/Kleinbuchstaben, Zahlen, Sonderzeichen
- Keine Wörterbuch-Wörter
- Keine persönlichen Daten
- Zufällig generiert bevorzugt