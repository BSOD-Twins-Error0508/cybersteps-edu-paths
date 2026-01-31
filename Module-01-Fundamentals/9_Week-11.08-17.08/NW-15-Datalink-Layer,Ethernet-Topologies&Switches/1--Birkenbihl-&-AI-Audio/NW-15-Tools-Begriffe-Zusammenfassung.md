# Kategorisierung Datenverbindungsschicht (Data Link Layer) - Layer 2

## Übersichtstabelle

|**Kategorie**|**Details**|
|---|---|
|**Verwendete Tools**|• **Systemeinstellungen/Einstellungen**: MAC-Adresse anzeigen (macOS: Systemeinstellungen → Netzwerk → Details → Hardware; Windows: Einstellungen → Netzwerk und Internet → Eigenschaften)<br>• **Terminal/Eingabeaufforderung**: Netzwerkschnittstellen anzeigen (macOS: `ifconfig en0`; Windows: `ipconfig /all`, `getmac`)<br>• **arp**: ARP-Tabelle anzeigen (beide Systeme: `arp -a`)<br>• **Wireshark**: Ethernet-Frames und MAC-Adressen analysieren<br>• **tcpdump**: Paketanalyse auf Layer 2 (macOS; Windows: WinDump)<br>• **PowerShell**: `Get-NetAdapter`, `Get-NetAdapterStatistics`<br>• **Device Manager/Geräte-Manager**: Netzwerkadapter verwalten (Windows)<br>• **Network Utility**: Netzwerkdiagnose (macOS: veraltet, ersetzt durch Terminal-Befehle)<br>• **Sysinternals Suite**: Netzwerk-Troubleshooting-Tools (Windows)<br>• **Switch-Management-Software**: Web-Interface oder CLI für Managed Switches<br>• **MAC Address Lookup**: Online-Tools zur OUI-Herstellersuche<br>• **Ethernet-Tester**: Hardware-Tools für Kabelprüfung<br>• **Network Analyzer**: Professionelle Layer-2-Analyse-Tools|
|**Technische Fachbegriffe**|• **Data Link Layer**: Datenverbindungsschicht (Layer 2 im OSI-Modell)<br>• **Frame**: Dateneinheit auf Layer 2 (strukturierte Datenrahmen)<br>• **MAC Address** (Media Access Control): Hardware-/physikalische Adresse<br>• **Physical Layer**: Physikalische Schicht (Layer 1)<br>• **Network Layer**: Netzwerkschicht (Layer 3)<br>• **Ethernet**: Verbreitete LAN-Technologie<br>• **Frame Check Sequence (FCS)**: Fehlerprüffeld im Frame-Trailer<br>• **Media Access Control**: Zugriffskontrolle auf gemeinsames Medium<br>• **CSMA/CD** (Carrier Sense Multiple Access with Collision Detection): Kollisionserkennung bei Ethernet<br>• **Hub**: Einfaches Layer-1-Gerät (Repeater)<br>• **Switch**: Intelligentes Layer-2-Gerät<br>• **MAC Address Table/CAM Table**: MAC-Adress-Zuordnungstabelle im Switch<br>• **Collision Domain**: Kollisionsbereich<br>• **Broadcast Domain**: Broadcast-Bereich<br>• **Half-Duplex**: Halbduplex (Senden oder Empfangen)<br>• **Full-Duplex**: Vollduplex (gleichzeitiges Senden und Empfangen)<br>• **NIC** (Network Interface Card): Netzwerkkarte<br>• **OUI** (Organizationally Unique Identifier): Herstellerkennung (erste 6 Hex-Ziffern)<br>• **EtherType**: Protokoll-Identifikator im Ethernet-Frame<br>• **Payload**: Nutzdaten im Frame<br>• **Broadcast Address**: Broadcast-Adresse (FF:FF:FF:FF:FF:FF)<br>• **Unicast**: Punkt-zu-Punkt-Übertragung<br>• **Multicast**: Übertragung an Gruppe<br>• **Twisted-Pair Cable**: Verdrilltes Kupferkabel (z.B. Cat5e, Cat6)<br>• **Coaxial Cable**: Koaxialkabel (veraltet)<br>• **Network Topology**: Netzwerk-Topologie (Anordnung der Geräte)<br>• **Star Topology**: Stern-Topologie<br>• **Bus Topology**: Bus-Topologie<br>• **Ring Topology**: Ring-Topologie<br>• **Mesh Topology**: Vermaschte Topologie<br>• **Hybrid Topology**: Hybrid-Topologie<br>• **Managed Switch**: Verwaltbarer Switch<br>• **Unmanaged Switch**: Nicht verwaltbarer Switch<br>• **VLAN** (Virtual LAN): Virtuelles lokales Netzwerk<br>• **STP** (Spanning Tree Protocol): Schleifenvermeidungsprotokoll<br>• **ARP** (Address Resolution Protocol): IP-zu-MAC-Auflösung|
|**Wichtige Vokabeln**|• **Lokales Netzwerksegment**: Bereich der direkten Layer-2-Kommunikation<br>• **Rohe Bits**: Unstrukturierte Binärdaten<br>• **Strukturierte Einheiten**: Organisierte Datenrahmen<br>• **Nachbarschaftsverkehr**: Lokale Netzwerkkommunikation<br>• **Hardware-Adresse**: Physikalische Gerätekennung<br>• **Fehlerprüfung**: Erkennung beschädigter Daten<br>• **Flusskontrolle**: Anpassung der Übertragungsrate<br>• **Gemeinsames Medium**: Von mehreren Geräten genutztes Kabel<br>• **Kollision**: Gleichzeitige Übertragung mehrerer Geräte<br>• **Verstümmelte Daten**: Durch Kollision beschädigte Übertragung<br>• **Multiport-Repeater**: Hub als Signalverstärker<br>• **Intelligentes Gerät**: Switch mit Lernfähigkeit<br>• **Weiterleitung**: Gezielte Frame-Übertragung<br>• **Broadcast**: Sendung an alle Geräte<br>• **Eingebrannte Kennung**: Fest in Hardware programmierte Adresse<br>• **Hexadezimalziffern**: 16er-System (0-9, A-F)<br>• **Hersteller-Kennung**: OUI zur Herstelleridentifikation<br>• **Sterntopologie**: Zentrale Verbindung aller Geräte<br>• **Zentrale Gerät**: Hub oder Switch in Sternmitte<br>• **Redundante Pfade**: Mehrfache Verbindungswege (Mesh)<br>• **Ausfalltoleranz**: Widerstandsfähigkeit gegen Geräteausfall<br>• **Verkabelung**: Physikalische Netzwerkverbindungen<br>• **Konfiguration**: Einrichtung und Einstellung<br>• **Backbone-Netzwerk**: Hauptverbindungsnetz<br>• **Kritische Verfügbarkeit**: Hohe Betriebssicherheit<br>• **Skalierbarkeit**: Erweiterungsfähigkeit<br>• **Fehlerbehebung**: Troubleshooting<br>• **Token-Passing**: Weitergabe eines Übertragungsrechts<br>• **Terminatoren**: Abschlusswiderstände an Kabelenden<br>• **Dual-Ring**: Doppelter Ring für Redundanz|

---

## 80/20-Zusammenfassung: Die wichtigsten 20% zum Verständnis von 80% der Datenverbindungsschicht

### **Die Datenverbindungsschicht (Layer 2): Der lokale Nachbarschafts-Manager**

**Layer 2 (Data Link Layer)** = Verwaltung der Kommunikation **innerhalb eines lokalen Netzwerksegments**

**Drei-Schichten-Überblick**:

```
┌─────────────────────────────────────────────┐
│ Layer 3 (Netzwerkschicht)                   │
│ → IP-Adressen                               │
│ → Routing zwischen Netzwerken               │
│ → "Verkehr zwischen Städten"                │
└─────────────────────────────────────────────┘
              ▲
              │
┌─────────────────────────────────────────────┐
│ Layer 2 (Datenverbindungsschicht)           │
│ → MAC-Adressen                              │
│ → Frames                                     │
│ → Kommunikation im lokalen Netz            │
│ → "Lokaler Nachbarschaftsverkehr"          │
└─────────────────────────────────────────────┘
              ▲
              │
┌─────────────────────────────────────────────┐
│ Layer 1 (Physikalische Schicht)            │
│ → Bits (0 und 1)                            │
│ → Kabel, Funkwellen                         │
│ → "Reine Signalübertragung"                │
└─────────────────────────────────────────────┘
```

**Analogie**:

- **Layer 1**: Die Straße (Bits fahren darauf)
- **Layer 2**: Lokale Postboten (verteilen innerhalb der Nachbarschaft anhand von Hausnummern = MAC-Adressen)
- **Layer 3**: Überregionale Post (verteilen zwischen Städten anhand von Städtenamen = IP-Adressen)

### **Die 5 Hauptaufgaben von Layer 2**

#### **1. Framing (Rahmenbildung) 📦**

**Was ist das?** Rohe Bits werden in **strukturierte Frames** organisiert

```
Bits von Layer 1: 01001000 01100101 01101100 01101100...

Layer 2 organisiert zu Frame:
┌────────────┬────────────┬──────────┬─────────┬─────┐
│  Header    │ Ziel-MAC   │ Quell-MAC│ Payload │ FCS │
│ (Präambel) │ (6 Bytes)  │ (6 Bytes)│ (Daten) │     │
└────────────┴────────────┴──────────┴─────────┴─────┘
```

**Frame-Struktur**: Header + Adressierung + Daten + Trailer

#### **2. Physical Addressing (MAC-Adressen) 🏠**

Geräte im lokalen Netz werden anhand **eindeutiger Hardware-Adressen** identifiziert

**MAC-Adresse** = 48-Bit (6 Bytes) Hexadezimal

**Format**: `00:1A:2B:3C:4D:5E`

```
00:1A:2B  :  3C:4D:5E
────────     ────────
   OUI       Geräte-ID
(Hersteller) (eindeutig)
```

**Beispiel-OUIs**:

- `00:1A:2B` → Cisco
- `00:50:56` → VMware
- `3C:22:FB` → Apple

#### **3. Error Detection (Fehlererkennung) ✅**

**Frame Check Sequence (FCS)** im Trailer erkennt Übertragungsfehler

```
Sender berechnet Prüfsumme → FCS im Frame
Empfänger berechnet erneut → Vergleich
Stimmt nicht überein? → Frame verwerfen
```

**Wichtig**: Layer 2 erkennt Fehler, **korrigiert sie aber nicht** (höhere Schichten erledigen das)

#### **4. Flow Control (Flusskontrolle) 🚦**

Verhindert, dass schneller Sender langsamen Empfänger überflutet

**Mechanismus**: Empfänger signalisiert "Pause" wenn Puffer voll

#### **5. Media Access Control (MAC) 🎛️**

Regelt, **wer wann senden darf** auf gemeinsamem Medium

**Früher (Shared Medium)**: CSMA/CD

- **C**arrier **S**ense: Lauschen, ob Leitung frei
- **M**ultiple **A**ccess: Mehrere Geräte teilen sich Medium
- **C**ollision **D**etection: Kollision erkennen → warten → erneut versuchen

**Heute (Switched Networks)**: Weitgehend obsolet, da Switches separate Kollisionsdomänen schaffen

### **Ethernet: Die dominierende LAN-Technologie**

**Ethernet** = Standard für kabelgebundene lokale Netzwerke (LANs)

**Geschichte**:

- **1970er**: Erfindung, gemeinsames Koaxialkabel
- **Heute**: Twisted-Pair-Kabel + Switches (moderne Netzwerke)

**Ethernet-Frame-Aufbau**:

```
┌──────────┬────────────┬────────────┬──────────┬─────────┬─────┐
│ Präambel │  Ziel-MAC  │ Quell-MAC  │ EtherType│ Payload │ FCS │
│ (8 Bytes)│  (6 Bytes) │  (6 Bytes) │ (2 Bytes)│(46-1500)│(4 B)│
└──────────┴────────────┴────────────┴──────────┴─────────┴─────┘
```

**Wichtige Felder**:

- **Ziel-MAC**: Empfänger im lokalen Netz
- **Quell-MAC**: Absender im lokalen Netz
- **EtherType**: Welches Protokoll? (z.B. 0x0800 = IPv4, 0x86DD = IPv6)
- **Payload**: Die eigentlichen Daten (z.B. IP-Paket)
- **FCS**: Fehlerprüfung

### **Hub vs. Switch: Der entscheidende Unterschied**

#### **Hub (Layer 1 - veraltet) 🔊**

**Funktion**: Dummer Multiport-Repeater

```
Signal kommt an Port 1 rein
          ↓
Hub sendet Signal an ALLE anderen Ports raus
          ↓
Alle Geräte empfangen ALLES (auch nicht für sie bestimmt)
```

**Eigenschaften**:

- ❌ Keine Intelligenz (schaut nicht auf MAC-Adressen)
- ❌ **Ein Kollisionsbereich** (alle Ports teilen sich Medium)
- ❌ **Half-Duplex** (Senden ODER Empfangen)
- ❌ **Ineffizient** (viele Kollisionen bei vielen Geräten)
- ❌ **Veraltet** (heute praktisch nicht mehr verwendet)

**Analogie**: Wie ein Lautsprecher – brüllt alles an alle raus

#### **Switch (Layer 2 - modern) 🧠**

**Funktion**: Intelligentes Weiterleitungsgerät

```
Frame kommt an Port 1 rein
          ↓
Switch liest Ziel-MAC-Adresse
          ↓
Switch sucht in MAC-Adress-Tabelle: Wo ist Ziel?
          ↓
Switch sendet Frame NUR an Port mit Ziel-Gerät
```

**MAC-Adress-Tabelle (Lernprozess)**:

```
Port | MAC-Adresse       | Gelernt durch
-----|-------------------|---------------
1    | 00:1A:2B:3C:4D:5E | Frame von Port 1
2    | AA:BB:CC:DD:EE:FF | Frame von Port 2
3    | 11:22:33:44:55:66 | Frame von Port 3
```

**Wie der Switch lernt**:

1. Frame kommt an Port 1 mit Quell-MAC `00:1A:2B:3C:4D:5E`
2. Switch: "Aha! Gerät mit MAC `00:1A:2B:3C:4D:5E` ist an Port 1!"
3. Eintrag in Tabelle
4. Nächstes Mal Frame an `00:1A:2B:3C:4D:5E` → nur an Port 1 senden

**Eigenschaften**:

- ✅ **Intelligent** (lernt MAC-Adressen)
- ✅ **Separate Kollisionsdomänen** pro Port (keine Kollisionen zwischen Ports!)
- ✅ **Full-Duplex** (gleichzeitiges Senden UND Empfangen)
- ✅ **Effizient** (gezielte Weiterleitung)
- ✅ **Standard in modernen Netzwerken**

**Analogie**: Wie ein intelligenter Postbote – kennt jede Adresse und bringt Post nur zum richtigen Haus

### **Hub vs. Switch: Vergleichstabelle**

|Merkmal|Hub|Switch|
|---|---|---|
|**Layer**|1 (Physikalisch)|2 (Data Link)|
|**Intelligenz**|❌ Keine|✅ MAC-Adress-Lernen|
|**Weiterleitung**|An ALLE Ports|Nur an Ziel-Port|
|**Kollisionsdomäne**|Eine (alle Ports)|Pro Port eine|
|**Broadcast-Domäne**|Eine|Eine (Standard)|
|**Duplex**|Half-Duplex|Full-Duplex|
|**Effizienz**|❌ Sehr niedrig|✅ Sehr hoch|
|**Status heute**|Veraltet|Standard|

### **Kollisionsdomäne vs. Broadcast-Domäne**

**Kollisionsdomäne** 💥:

```
Bereich, wo gleichzeitige Übertragungen kollidieren können

Hub: EINE Kollisionsdomäne (alle Ports)
┌─────────────────────────────────┐
│ [PC1] [PC2] [PC3] [PC4]         │
│  Alle teilen sich das Medium    │
└─────────────────────────────────┘

Switch: Separate Kollisionsdomäne pro Port
┌───┐ ┌───┐ ┌───┐ ┌───┐
│PC1│ │PC2│ │PC3│ │PC4│
└─┬─┘ └─┬─┘ └─┬─┘ └─┬─┘
  └─────┼─────┼─────┘
      [Switch]
    Keine Kollisionen!
```

**Broadcast-Domäne** 📢:

```
Bereich, wo Broadcast-Frames alle erreichen

Hub/Switch: EINE Broadcast-Domäne
Frame an FF:FF:FF:FF:FF:FF → alle Ports

Router: Trennt Broadcast-Domänen
Broadcasts werden NICHT weitergeleitet
```

### **MAC-Adressen: Die Hardware-Identität**

**MAC (Media Access Control) Address** = 48-Bit Hardware-Adresse

**Format**: 6 Bytes Hexadezimal

```
00:1A:2B:3C:4D:5E
│       │
│       └─ Geräte-ID (vom Hersteller vergeben)
└───────── OUI (Hersteller-ID)
```

**Eigenschaften**:

- ✅ **Weltweit eindeutig** (theoretisch)
- ✅ **Vom Hersteller eingebrannt** (fest in NIC programmiert)
- ✅ **Für Layer-2-Kommunikation** (innerhalb lokales Netz)
- ⚠️ **Kann softwareseitig geändert werden** (MAC-Spoofing)

**Spezielle MAC-Adressen**:

- **Broadcast**: `FF:FF:FF:FF:FF:FF` (an alle im lokalen Netz)
- **Multicast**: Beginnt mit `01:00:5E` (IPv4 Multicast)

**MAC vs. IP**:

```
MAC-Adresse:
- Layer 2 (Datenverbindungsschicht)
- Lokales Netz
- Hardware-basiert
- Ändert sich normalerweise nicht
- Beispiel: 00:1A:2B:3C:4D:5E

IP-Adresse:
- Layer 3 (Netzwerkschicht)
- Globales Internet
- Software-basiert
- Ändert sich (DHCP, neue Netzwerke)
- Beispiel: 192.168.1.100
```

**Warum beide?**

- **IP**: Findet den Weg durchs Internet (Routing)
- **MAC**: Liefert im lokalen Netz aus (Switching)

**Analogie**:

- **IP-Adresse** = Postleitzahl + Straße + Hausnummer (für Routing)
- **MAC-Adresse** = Name an der Klingel (für lokale Zustellung)

### **MAC-Adresse finden (Windows 11)**

**Methode 1: Einstellungen (GUI)**

1. **Einstellungen** → **Netzwerk und Internet**
2. **Eigenschaften** der aktiven Verbindung
3. Suche **Physische Adresse (MAC)**

**Methode 2: Kommandozeile**

```cmd
ipconfig /all
```

Suche nach **Physische Adresse** unter deinem Adapter

**Methode 3: PowerShell**

```powershell
Get-NetAdapter | Select-Object Name, MacAddress
```

**Methode 4: getmac**

```cmd
getmac /v
```

### **Netzwerk-Topologien: Wie Geräte verbunden sind**

**Topologie** = Anordnung/Layout der Netzwerkverbindungen

#### **1. Bus-Topologie 🚌 (veraltet)**

```
[PC1]──┬──[PC2]──┬──[PC3]──┬──[PC4]
       │         │         │
    Gemeinsames Kabel (Bus)
  Terminatoren an beiden Enden
```

**Eigenschaften**:

- ✅ Einfach, günstig
- ❌ Kabel-Ausfall → ganzes Netz down
- ❌ Viele Kollisionen
- ❌ **Veraltet**

#### **2. Ring-Topologie 🔄 (selten)**

```
     [PC1]
    ↗     ↘
[PC4]       [PC2]
    ↖     ↙
     [PC3]
```

**Eigenschaften**:

- Token-Passing (ordentliche Übertragung)
- ❌ Ausfall eines Geräts → Ring bricht
- ❌ Weniger verbreitet

#### **3. Stern-Topologie ⭐ (STANDARD!)**

```
      [PC1]
        │
[PC2]─[Switch]─[PC3]
        │
      [PC4]
```

**Eigenschaften**:

- ✅ **Heute Standard für LANs**
- ✅ Einfach zu installieren/verwalten
- ✅ Ausfall eines Kabels → nur 1 Gerät betroffen
- ✅ Einfach erweiterbar
- ✅ Mit Switch: Separate Kollisionsdomänen + Full-Duplex
- ❌ Switch-Ausfall → ganzes Segment down
- ❌ Mehr Kabel nötig

**Warum Stern am beliebtesten?**

- Zuverlässig
- Skalierbar
- Effizient (mit Switch)
- Einfach zu troubleshooten

#### **4. Mesh-Topologie 🕸️ (hochverfügbar)**

```
Full Mesh:
[PC1]─────[PC2]
  │  ╲   ╱  │
  │   ╲ ╱   │
  │   ╱ ╲   │
  │  ╱   ╲  │
[PC3]─────[PC4]
(Jeder mit jedem verbunden)
```

**Eigenschaften**:

- ✅ **Höchste Redundanz**
- ✅ Ausfall einer Verbindung → alternative Wege
- ❌ Sehr teuer (viele Kabel)
- ❌ Komplex zu konfigurieren
- 🎯 **Verwendung**: Internet-Backbone, kritische Netzwerke

#### **5. Hybrid-Topologie 🔀**

```
Kombination mehrerer Topologien
z.B. mehrere Stern-Netzwerke über Backbone verbunden
```

**Eigenschaften**:

- ✅ Flexibel, skalierbar
- ❌ Komplex

### **Heim-Netzwerk-Beispiel**

**Typisches Setup**:

```
      Internet
         │
    [Router/Modem]
         │
     (Wi-Fi)
   ╱    │    ╲
[Laptop] [Smartphone] [Smart-TV]
```

**Topologie**: **Stern** (alle Geräte verbinden sich zentral mit Router)

### **Praktisches Beispiel: Switch-Forwarding**

**Szenario**:

```
Port 1: PC-A (MAC: AA:AA:AA:AA:AA:AA)
Port 2: PC-B (MAC: BB:BB:BB:BB:BB:BB)
Port 3: PC-C (MAC: CC:CC:CC:CC:CC:CC)

PC-A will Frame an PC-C senden
```

**Ablauf**:

```
1. PC-A sendet Frame:
   Quell-MAC: AA:AA:AA:AA:AA:AA
   Ziel-MAC:  CC:CC:CC:CC:CC:CC

2. Frame kommt an Switch Port 1

3. Switch lernt:
   "MAC AA:AA:AA:AA:AA:AA ist an Port 1"
   → Eintrag in MAC-Tabelle

4. Switch schaut Ziel-MAC an:
   "Wo ist CC:CC:CC:CC:CC:CC?"
   → In Tabelle: Port 3

5. Switch sendet Frame NUR an Port 3

6. PC-C empfängt Frame
   PC-A und PC-B empfangen NICHTS (effizient!)
```

**Falls Ziel-MAC unbekannt**:

```
Switch kennt Ziel-MAC nicht
→ Sendet Frame an ALLE Ports (außer Quell-Port)
→ "Flooding"
→ Richtiges Gerät antwortet
→ Switch lernt MAC-Adresse
```

### **Kernbotschaft**

**Layer 2 (Datenverbindungsschicht)** verwaltet die **lokale Netzwerkkommunikation**:

**Frames** = Strukturierte Dateneinheiten mit MAC-Adressen **MAC-Adressen** = Hardware-Identität für Layer-2-Kommunikation **Switches** = Intelligente Geräte, die Frames gezielt weiterleiten

**Evolution**:

```
Früher: Hub + Shared Medium
       → Viele Kollisionen, Half-Duplex, ineffizient

Heute: Switch + Stern-Topologie
      → Separate Kollisionsdomänen, Full-Duplex, hocheffizient
```

**Der Switch** war die **Revolution im LAN**:

- Intelligente Weiterleitung
- Separate Kollisionsdomänen pro Port
- Full-Duplex-Betrieb
- Drastisch höhere Effizienz

**Zusammenspiel mit anderen Layers**:

- **Layer 1**: Bits übertragen
- **Layer 2**: Frames im lokalen Netz verteilen (MAC-Adressen)
- **Layer 3**: Pakete zwischen Netzwerken routen (IP-Adressen)

**Analogie finale**: Layer 2 ist wie ein **lokales Postzentrum**, das Post innerhalb einer Stadt/Nachbarschaft verteilt (MAC = Hausnummern), während Layer 3 wie das **überregionale Postsystem** ist, das zwischen Städten vermittelt (IP = Städtenamen)! 📬🏘️🔀