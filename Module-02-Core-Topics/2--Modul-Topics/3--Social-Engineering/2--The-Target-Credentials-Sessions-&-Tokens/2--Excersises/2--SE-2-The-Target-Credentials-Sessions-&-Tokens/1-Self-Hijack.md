Wie einem Baby die Kekse zu klauen_

**Ziel**

Erstellen Sie eine einfache Flask-Webanwendung, die Session-Cookies zur Authentifizierung verwendet, und führen Sie dann einen Session-Hijacking-Angriff gegen Ihre eigene Anwendung durch.

**Anleitung**

**Teil 1: Erstellen der Anwendung**

Schreiben Sie ein Python-Skript namens `my_app.py` mit Flask. Die Anwendung muss die folgenden Spezifikationen erfüllen:

1. Sie muss eine Anmeldeseite unter der Root-URL (`/`) haben, die ein Formular mit den Feldern `Benutzername` und `Passwort` anzeigt.
2. Sie sollte ein fest kodiertes Benutzerwörterbuch haben, z.B. `users = {'user': 'password'}`.
3. Wenn ein Benutzer die korrekten Anmeldedaten eingibt, sollte der Server seinen Benutzernamen in der `Session` speichern und ihn auf eine `geschützte` Seite umleiten.
    1. Benutze das Flask `session` Objekt [https://flask.palletsprojects.com/en/stable/api/#flask.session](https://flask.palletsprojects.com/en/stable/api/#flask.session)
4. Die `/protected` Seite sollte eine Willkommensnachricht anzeigen, wie "Welcome, user!", aber nur wenn der Benutzer eingeloggt ist. Wenn er nicht eingeloggt ist (d.h. keine gültige Session), sollte sie ihn zurück zur Login-Seite weiterleiten.
5. Verwenden Sie einen einfachen, nicht zufälligen `app.secret_key`.

**Teil 2: Entführung der Sitzung**

1. Führen Sie Ihr fertiges Skript von Ihrem Terminal aus: `python3 meine_app.py`.
2. **Browser A (z. B. Chrome):** Navigieren Sie zur Anmeldeseite Ihrer Anwendung. Melden Sie sich mit den richtigen Anmeldedaten an.
3. Verwenden Sie in Browser A die Entwicklertools, um das "Session"-Cookie zu finden und seinen Wert zu kopieren.
4. **Browser B (z. B. Firefox oder ein neues Inkognito-Fenster):** Navigieren Sie zur Anmeldeseite Ihrer Anwendung. Sie sollten nicht eingeloggt sein.
5. Verwenden Sie in Browser B die Entwicklertools, um manuell ein neues Cookie für Ihre lokale Website zu erstellen. Nennen Sie es `session` und fügen Sie den Wert ein, den Sie aus Browser A kopiert haben.
6. Aktualisieren Sie die Seite in Browser B. Sie sollten nun Zugriff auf den "geschützten" Bereich haben.

**Vorlage**

Reichen Sie Ihr Python-Skript (`my_app.py`) und einen Screenshot von Browser B ein, der den erfolgreichen Session-Hijack zeigt.

