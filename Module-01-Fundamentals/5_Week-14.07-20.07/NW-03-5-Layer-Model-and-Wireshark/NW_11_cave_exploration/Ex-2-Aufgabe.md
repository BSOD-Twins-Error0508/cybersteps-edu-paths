# Cave Exploration

_How many layers it takes layers to say 'hello'?_

**Goal**

Analyze an ICMP Echo Request packet, identify the necessary filter, describe information at each layer, and note any missing layers compared to the HTTP packet.

**Instructions**

1. Start a Wireshark capture on your main network interface.
2. Open your terminal and run the command `ping -c 1 8.8.8.8`.
3. Stop the Wireshark capture.
4. What display filter do you need to use to see only the ping (ICMP) traffic? Apply this filter.
5. Select the "Echo (ping) request" packet sent from your computer.
6. Examine the Packet Details pane. Describe the key information found at each relevant layer (similar to Exercise 1: Data Link, Network).
7. Compare the layers present in this ICMP packet to the layers present in the HTTP packet from Exercise 1. Is there a distinct Transport Layer header present for ICMP? What might this difference imply about how ICMP operates within the network stack?

**Submission**

Submit the display filter used, the description of information per layer for the ping request, and your analysis of the layer differences compared to HTTP and its implications.

---
---
# Höhlenforschung

_Wie viele Schichten braucht es, um „Hallo” zu sagen?_

**Ziel**

Analysieren Sie ein ICMP-Echo-Request-Paket, identifizieren Sie den erforderlichen Filter, beschreiben Sie die Informationen auf jeder Schicht und notieren Sie alle fehlenden Schichten im Vergleich zum HTTP-Paket.

**Anweisungen**

1. Starten Sie eine Wireshark-Erfassung auf Ihrer Hauptnetzwerkschnittstelle.
2. Öffnen Sie Ihr Terminal und führen Sie den Befehl „ping -c 1 8.8.8.8“ aus.
3. Beenden Sie die Wireshark-Erfassung.
4. Welchen Anzeigefilter müssen Sie verwenden, um nur den Ping-Verkehr (ICMP) anzuzeigen? Wenden Sie diesen Filter an.
5. Wählen Sie das von Ihrem Computer gesendete „Echo (Ping)-Anforderung”-Paket aus.
6. Untersuchen Sie den Bereich „Paketdetails”. Beschreiben Sie die wichtigsten Informationen, die Sie auf jeder relevanten Schicht finden (ähnlich wie in Übung 1: Datenverbindung, Netzwerk).
7. Vergleichen Sie die in diesem ICMP-Paket vorhandenen Schichten mit den Schichten im HTTP-Paket aus Übung 1. Gibt es einen eindeutigen Transportschicht-Header für ICMP? Was könnte dieser Unterschied über die Funktionsweise von ICMP innerhalb des Netzwerkstacks aussagen?

**Einreichung**

Reichen Sie den verwendeten Anzeigefilter, die Beschreibung der Informationen pro Schicht für die Ping-Anfrage und Ihre Analyse der Schichtunterschiede im Vergleich zu HTTP und deren Auswirkungen ein.

---
---

**Datenverbindungsschicht:** 
Welches Protokoll wird laut dem Feld „Type“ in diesem Frame übertragen?
ipv4

**Netzwerkschicht:** 
Welches Protokoll wird hier angezeigt? 
icmp 

Wie lauten die Quell- und Ziel-IP-Adressen?
192.168.0.92
8.8.8.8

**Transportschicht:** 
Welches Protokoll wird hier angezeigt? 
Gibt es nicht

Wie lauten die Quell- und Zielportnummern?
Gibt es nicht 

**Anwendungsschicht:** 
Welches Protokoll wird hier angezeigt? 
Gibt es nicht

Welche spezifischen Anforderungsbefehle und angeforderten Ressourcen können Sie sehen?
Gibt es nicht 

**Aber es gibt Internet Control Message Protocol:**
Welches Protokoll wird laut dem Feld „Type“ in diesem Frame übertragen?
Echo (ping) request(8)

Data: 6162636465666768696a6b6c6d6e6f7071727374757677616263646566676869
"""