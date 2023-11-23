# [Echtzeitdatenbank](https://firebase.google.com/docs/database?hl=de) #

[**Zurück zum Haupttutorial**](tutorial.md)

### Realtime Database ###

Gehen Sie über das Seitenmenü zum Modul "**Realtime Database**" und klicken Sie auf "Datenbank erstellen". Damit initialisieren Sie die Einrichtung der Datenbank.

![firebase33_db.png](pix%2Ffirebase33_db.png)

Sie können im nächsten Dialog den **Standort Ihrer Daten** festlegen. Wie Sie sehen ist die Auswahl auf 3 Kontinente beschränkt. Wählen Sie einen aus!

![firebase34_db.png](pix%2Ffirebase34_db.png)

Im nächsten Dialog können Sie wählen, ob sie **mit oder ohne Sicherheitsregeln starten**. Beginnen Sie mit privaten Daten:

![firebase35_db.png](pix%2Ffirebase35_db.png)

Danach gelangen Sie in die **Verwaltung Ihrer Datenbank** in den **Datenbereich**. In der ersten Zeile sehen Sie die **URL Ihrer Datenbank** (_Im Format:_ ```https:// DATABASE_NAME . REGION .firebasedatabase.app```)!

![firebase36_db.png](pix%2Ffirebase36_db.png)

Sie können hier Ihre Daten sehen und sehr einfach exportieren. Diese noSQL Datenbank speicher im **JSON Format**:

![firebase37_db.png](pix%2Ffirebase37_db.png)

Hier der **Export**:

```json
{
  "beitraege": {
    "beitrag-1": {
      "autor": "makno",
      "id": 1,
      "inhalt": "Inhalt von Eintrag 1",
      "titel": "Eintrag 1"
    },
    "eintrag-2": {
      "id": 2,
      "inhalt": "Inhaltvon Eintrag 2",
      "titel": "Eintrag 2"
    }
  }
}
```

[**Zurück zum Haupttutorial**](tutorial.md)



## [WebApp Implementierung](https://firebase.google.com/docs/database/web/start?hl=de) ##

Fügen Sie zuerst die **Bibliothek für die Echtzeitdatenbank** im head der [index.html](../public/index.html) ein:

``` html
<script src="https://www.gstatic.com/firebasejs/10.5.0/firebase-database-compat.js"></script>
```

Dann ergänzen Sie die **Konfiguration** (```firebaseConfig```) um die Datenbank:

``` javascript
databaseURL: "https:// DATABASE_NAME . REGION .firebasedatabase.app"
```

Zum Schluss muss die Datenbank in der WebApp noch **initialisiert** werden:

``` javascript
const database = firebase.database();
```

Unter diesen Links finden Sie die grundlegenden **Datenbankoperationen (CRUD)** 

* [**C**reate](https://firebase.google.com/docs/database/web/read-and-write?hl=de#read_data)
* [**R**ead](https://firebase.google.com/docs/database/web/read-and-write?hl=de#read_data)
* [**U**pdate](https://firebase.google.com/docs/database/web/read-and-write?hl=de#updating_or_deleting_data)
* [**D**elete](https://firebase.google.com/docs/database/web/read-and-write?hl=de#updating_or_deleting_data)

## Aufgabe ##

**Implementieren** Sie die Funktionalitäten, die Sie für Ihre WebApp brauchen! 

[**Zurück zum Haupttutorial**](tutorial.md)