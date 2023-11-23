# WebApp mit Firebase - Tutorial

[Zurück zur Readme](../readme.md)

In diesem Tutorial wird die JetBrains IDE [Webstorm](https://www.jetbrains.com/de-de/webstorm/) verwendet.
Die Anleitung ist so konzipiert, dass Sie zu Beginn Schritt für Schritt vorgehen können- später wird jedoch mehr und mehr auf Quellen in Firebase, Github u.ä. verwiesen.

In der Google Dokumentation wird vor allem die **"modulare Web-API**" hervorgehoben, welche effizienteren Code via "[Tree-Shaking](https://webpack.js.org/guides/tree-shaking/)" und Modularität und damit bessere Integration in gängige JavaScript Frameworks bietet. Die "**Web-Namespace-API**" (so genannt, weil nur in einem Namespace "firebase") ist die etwas klassischere Variante, die einfacher zu verstehen und schneller zu implementieren ist.

**Dieses Tutorial verwendet die "Web-Namespace-API"!**

_Anmerkung_: Da hier Cloud Produkte im Einsatz sind, werden zum Großteil externe Bibliotheken und Dienste von Google in Anspruch genommen.  

* Laden Sie alle Node Module mit ```npm install``` (Sie können Sie gegebenenfalls [erneuern](../readme.md))
* Testen Sie, ob Ihre Entwicklungsumgebung korrekt eingerichtet ist:
  * Rufen Sie ```npm run watch``` und dann testen Sie die 
  * Site am Browser mit Adresse http://localhost:8123 ! 
* [Erstellen Sie ein Firebase Projekt](tutorial_01_firebase_projekt.md)
* Fügen Sie eine [Firebase WebApp](tutorial_02_firebase_webapp.md) zu Ihrem Projekt hinzu. 
* Fügen Sie [Authentifizierung](tutorial_03_firebase_auth.md) hinzu und bauen Sie diese aus
* Binden Sie die [Echtzeitdatenbank](tutorial_04_firebase_db.md) (Realtime Database) ein und bauen Sie eine rudimentäre CRUD Funktionalität (je nachdem, was für Ihre WebApp gebraucht wird)
* _Optional_: Binden Sie [Dateien via Stroage](tutorial_05_firebase_storage.md) ein!

Unter [Troubleshooting](tutorial_troubleshooting.md) findet man Lösungen zu Problemen.

[Zurück zur Readme](../readme.md)
