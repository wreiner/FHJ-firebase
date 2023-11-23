# [Storage](https://firebase.google.com/docs/storage?hl=de) #

[**Zurück zum Haupttutorial**](tutorial.md)

![firebase38_storage.png](pix%2Ffirebase38_storage.png)

Die Einrichtung ist denkbar einfach:

![firebase39_storage.png](pix%2Ffirebase39_storage.png)

![firebase40_storage.png](pix%2Ffirebase40_storage.png)

![firebase41_storage.png](pix%2Ffirebase41_storage.png)

![firebase42_storage.png](pix%2Ffirebase42_storage.png)

[**Zurück zum Haupttutorial**](tutorial.md)



## [WebApp Implementierung](https://firebase.google.com/docs/storage/web/start?hl=de) ##

Fügen Sie zuerst die **Bibliothek für die Echtzeitdatenbank** im head der [index.html](../public/index.html) ein:

``` html
<script src="https://www.gstatic.com/firebasejs/10.5.0/firebase-storage-compat.js"></script>
```

Dann kontrollieren Sie die **Konfiguration** (```firebaseConfig```) um Ihre Storage URL:

``` javascript
databaseURL: "project-id .appspot.com"
```

Zum Schluss muss der Storage in der WebApp noch **initialisiert** werden:

``` javascript
const storage = firebase.storage();
```

Unter [diesem Link](https://github.com/firebase/quickstart-js/blob/master/storage/index.html) finden Sie eine Beispielimplementierung zum Storage. Fügen Sie nach eigenem Belieben Bilder oder andere Daten hinzu- kombinieren Sie ggfls mit Daten aus der Realtime Database.

**Anmerkung**: Die Verwendung des Storage ist nicht erforderlich.

[**Zurück zum Haupttutorial**](tutorial.md)