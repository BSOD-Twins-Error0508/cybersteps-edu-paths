# The Onion

_Peel back the layers_

**Goal**

Analyze an HTTP request packet to identify the protocols and key information at each relevant layer of the 5-layer model.

**Instructions**

1. Start a Wireshark capture on your main network interface.
2. Open a web browser and navigate _specifically_ to `http://neverssl.com`.
3. Wait for the page to load completely, then stop the Wireshark capture.
4. In Wireshark's display filter bar, type `http` and press Enter.
5. Select the packet that shows "GET / HTTP/1.1" in the Info column or Packet Details (this is the request from your browser to the server).
6. Examine the Packet Details pane for this selected packet. Describe the key information found at each of the following layers:
    - **Data Link Layer:** What protocol does the 'Type' field indicate is being carried inside this frame?
    - **Network Layer:** What protocol is shown here? What are the source and destination IP addresses?
    - **Transport Layer:** What protocol is shown here? What are the source and destination port numbers?
    - **Application Layer:** What protocol is shown here? What specific request command and requested resource can you see?

**Submission**

Submit your description of the protocol and key information found at each of the four layers listed for the HTTP GET request packet.

---
---
# Die Zwiebel

_Die Schichten abziehen_

**Ziel**

Analysieren Sie ein HTTP-Anforderungspaket, um die Protokolle und Schlüsselinformationen auf jeder relevanten Schicht des 5-Schichten-Modells zu identifizieren.

**Anleitung**

1. Starten Sie eine Wireshark-Erfassung auf Ihrer Hauptnetzwerkschnittstelle.
2. Öffnen Sie einen Webbrowser und navigieren Sie _speziell_ zu `http://neverssl.com`.
3. Warten Sie, bis die Seite vollständig geladen ist, und beenden Sie dann die Wireshark-Erfassung.
4. Geben Sie in der Anzeigefilterleiste von Wireshark `http` ein und drücken Sie die Eingabetaste.
5. Wählen Sie das Paket aus, das in der Spalte „Info“ oder „Paketdetails“ „GET / HTTP/1.1“ anzeigt (dies ist die Anfrage Ihres Browsers an den Server).
6. Untersuchen Sie den Bereich „Packet Details“ für dieses ausgewählte Paket. Beschreiben Sie die wichtigsten Informationen, die Sie in den folgenden Schichten finden:
- **Datenverbindungsschicht:** Welches Protokoll wird laut dem Feld „Type“ in diesem Frame übertragen?
- **Netzwerkschicht:** Welches Protokoll wird hier angezeigt? Wie lauten die Quell- und Ziel-IP-Adressen?
    - **Transportschicht:** Welches Protokoll wird hier angezeigt? Wie lauten die Quell- und Zielportnummern?
- **Anwendungsschicht:** Welches Protokoll wird hier angezeigt? Welche spezifischen Anforderungsbefehle und angeforderten Ressourcen können Sie sehen?

**Einreichung**

Reichen Sie Ihre Beschreibung des Protokolls und der wichtigsten Informationen ein, die Sie in jeder der vier für das HTTP-GET-Anforderungspaket aufgeführten Schichten gefunden haben.



**Datenverbindungsschicht:** 
Welches Protokoll wird laut dem Feld „Type“ in diesem Frame übertragen?
ipv4

**Netzwerkschicht:** 
Welches Protokoll wird hier angezeigt? 
IP

Wie lauten die Quell- und Ziel-IP-Adressen?
192.168.0.92
34.223.124.45

**Transportschicht:** 
Welches Protokoll wird hier angezeigt? 
TCP 

Wie lauten die Quell- und Zielportnummern?
65510
80

**Anwendungsschicht:** 
Welches Protokoll wird hier angezeigt? 
http

Welche spezifischen Anforderungsbefehle und angeforderten Ressourcen können Sie sehen?
Request Method: GET
Request URI:  /
Request Version: HTTP/1.1

