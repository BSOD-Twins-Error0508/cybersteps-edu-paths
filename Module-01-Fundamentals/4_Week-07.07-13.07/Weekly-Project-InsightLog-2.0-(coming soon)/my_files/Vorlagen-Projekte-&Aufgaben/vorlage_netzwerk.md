# 🌐 [Aufgaben-Titel]

**Kurs:** [Kursname] | **Datum:** [TT.MM.JJJJ]

---

## 📋 Aufgabenstellung

**Thema:** [z.B. Paketanalyse & Protokolle]

**Ziel:** [Kurze Beschreibung]

**Protokolle:**
- [ ] TCP/UDP
- [ ] ICMP
- [ ] HTTP/DNS

---

## ⚙️ Netzwerk-Umgebung

```bash
Schnittstelle:  en0 (Wi-Fi)
Lokale IP:      192.168.1.100
Gateway:        192.168.1.1
DNS:            8.8.8.8
```

**Konfiguration prüfen:**
```bash
ifconfig en0
netstat -nr
```

---

## 📦 Paketanalyse

### Capture Setup
```
Tool:           Wireshark 4.0.x
Schnittstelle:  en0
Dauer:          30 Sekunden
Pakete:         427 erfasst
```

**Traffic erzeugen:**
```bash
ping -c 5 8.8.8.8
curl http://example.com
nslookup google.com
```

---

### Paket #1: ICMP Echo Request

**Richtung:** 192.168.1.100 → 8.8.8.8

**Layer 2 - Ethernet:**
```
Quell-MAC:      aa:bb:cc:dd:ee:ff
Ziel-MAC:       11:22:33:44:55:66 (Router)
```

**Layer 3 - IP:**
```
Quell-IP:   192.168.1.100
Ziel-IP:    8.8.8.8
Protokoll:  ICMP (1)
TTL:        64
```

**Layer 4 - ICMP:**
```
Typ:        8 (Echo Request)
Sequenz:    1
Daten:      56 Bytes
```

**Wireshark Filter:** `icmp && ip.src == 192.168.1.100`

---

### Paket #2: ICMP Echo Reply

**Richtung:** 8.8.8.8 → 192.168.1.100

**Änderungen:**
- IPs getauscht (8.8.8.8 → 192.168.1.100)
- MACs getauscht
- ICMP Typ: 0 (Reply)
- TTL: 117 (anders durch Router-Hops)

**Analyse:**
- Roundtrip-Zeit: ~18ms
- Kein Paketverlust
- MAC-Adressen ändern sich bei jedem Hop

---

### Paket #3: TCP Three-Way Handshake

**Verbindung zu example.com (93.184.216.34:80)**

| Schritt | Flags | Seq | Ack | Beschreibung |
|---------|-------|-----|-----|--------------|
| 1 | SYN | 1000 | - | Client initiiert |
| 2 | SYN-ACK | 2000 | 1001 | Server antwortet |
| 3 | ACK | 1001 | 2001 | Verbindung hergestellt |

**Filter:** `tcp.flags.syn == 1 && tcp.port == 80`

---

## 📊 Traffic Übersicht

| Protokoll | Pakete | Zweck |
|-----------|--------|-------|
| TCP | 285 (66%) | HTTP/HTTPS |
| UDP | 48 (11%) | DNS |
| ICMP | 10 (2%) | Ping |

---

## ✅ Fragen & Antworten

**Frage 1:** Was ist die Quell-MAC im ICMP Request?  
**Antwort 1:** `aa:bb:cc:dd:ee:ff` - MAC-Adresse meines Computers (Layer 2)

**Frage 2:** Warum ist die Ziel-MAC die des Routers und nicht 8.8.8.8?  
**Antwort 2:** MAC-Adressen gelten nur im lokalen Netzwerk. Da 8.8.8.8 nicht im lokalen Subnet ist, wird das Paket an den Router (Default Gateway) gesendet.

**Frage 3:** Wie ändern sich die Adressen zwischen Request und Reply?  
**Antwort 3:** 
- IPs getauscht: 100 ↔ 8.8.8.8
- MACs getauscht (aber andere MACs da über Router)
- ICMP Typ: 8 → 0
- TTL unterschiedlich durch Router-Hops

---

## 💡 Erkenntnisse

**Gelernt:**
- MAC vs IP Adressierung (Layer 2 vs 3)
- TCP Three-Way Handshake (SYN, SYN-ACK, ACK)
- TTL Dekrement bei jedem Router-Hop
- Protokoll-Encapsulation

**Wireshark Filter:**
```
icmp                     # ICMP Pakete
tcp.port == 80           # HTTP
ip.addr == 192.168.1.100 # Bestimmte IP
```

---

## 📸 Screenshots

- [📷 Paket Details](./screenshots/paket_details.png)
- [📷 Protokoll-Hierarchie](./screenshots/protokolle.png)

---

**Status:** ✅ Abgeschlossen | **Zeit:** ~[X] Std.
