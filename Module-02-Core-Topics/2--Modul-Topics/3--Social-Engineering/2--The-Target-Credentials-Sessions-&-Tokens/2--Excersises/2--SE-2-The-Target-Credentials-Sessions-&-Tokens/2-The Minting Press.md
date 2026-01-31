Warum eine Wertmarke stehlen, wenn man seine eigene drucken kann?

**Ziel**

Erstellen einer einfachen Flask-API, die JSON-Web-Token (JWTs) korrekt ausgibt und validiert, um einen bestimmten Endpunkt zu schützen.

**Anleitung**

Schreiben Sie ein Python-Skript mit Flask und PyJWT, das die folgenden Aufgaben erfüllt:

1. Verfügt über einen öffentlichen Endpunkt `/`, der eine einfache Willkommensnachricht zurückgibt.
2. Hat einen `/login` Endpunkt, der eine POST Anfrage mit einem Dummy `Benutzername` und `Passwort` annimmt. Wenn sie mit einem hartkodierten Wert übereinstimmen, sollte er ein JWT erzeugen.
    - Der JWT-Payload muss den "Benutzernamen" und eine Ablaufzeit (`exp`) enthalten, die auf 5 Minuten in der Zukunft eingestellt ist.
    - Es sollte das JWT an den Benutzer zurückgeben.
3. Hat einen geschützten Endpunkt `/protected`. Dieser Endpunkt sollte:
    - Ein JWT im `Authorization: Bearer <token>"-Header erwarten.
    - Die Signatur und die Gültigkeitsdauer des Tokens validieren.
    - Wenn es gültig ist, eine Nachricht wie "Willkommen {Benutzername}, Sie haben Zugang!" zurückgeben.
    - Wenn es ungültig ist oder fehlt, wird ein Fehler 401 Unauthorized zurückgegeben.

Sie müssen die erforderlichen Bibliotheken installieren: `pip3 install Flask PyJWT`.

**Einreichung**

Reichen Sie Ihr vollständiges Python-Skript ein (Datei `.py`).

