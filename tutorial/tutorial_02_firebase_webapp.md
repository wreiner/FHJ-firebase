# WebApp zu Firebase hinzufügen #

[**Zurück zum Haupttutorial**](tutorial.md)

Auf Ihrer Firebase Haupseite können Sie **Unterstützung für verschiedene Plattformen** hinzufügen. I, Falle dieses Tutorials ist es eine **WebApp**:

![firebase14_webapp.png](pix%2Ffirebase14_webapp.png)

**Registrieren** Sie die App. Hosting wird später hinzugefügt und bleibt deaktiviert.

![firebase15_webapp.png](pix%2Ffirebase15_webapp.png)

Sie bekommen nun die Anweisung das **Firebase SDK** zu installieren. Dieses kann via **npm oder URLs innerhalb von script**-Tags importiert werden. Wählen Sie für dieses Projekt dioe Option "**&lt;script&gt;-Tag verwenden**"

![firebase16_webapp.png](pix%2Ffirebase16_webapp.png)

Folgen Sie hier **NICHT** den Anweisungen und fügen Sie das Script vor dem End-Tag des body-Elements in Ihrer [index.html](../public/index.html) ein!

In Ihrer Projektübersicht sehen Sie die unterstützten Plattformen als Icons mit Namen, welche per Klick knfiguriert werden können.

![firebase17_webapp.png](pix%2Ffirebase17_webapp.png)
![firebase18_webapp.png](pix%2Ffirebase18_webapp.png)

Sie gelangen so zu Ihren **Projekteinstellungen** (Ihr Projekt, Ihre Apps, etc) unnd können Ihre WebApp weiter konfigurieren. Hier sehen bei Bedarf nochmal die SDK Einrichtung, aber auch die **Konfiguration**. Wählen Sie letztere.

![firebase19_webapp.png](pix%2Ffirebase19_webapp.png)

Sie sehen die **Einstellungen zu Ihrer App**, die Sie bereits beim Hinzufügen der App nach [index.html](../public/index.html) kopiert haben.

Hier sehen sie die Einstellungen zuz Ihrem [Projekt](https://firebase.google.com/docs/projects/learn-more?hl=de):

* [apiKey](https://firebase.google.com/docs/reference/js/v8/firebase.auth.Config#apikey), ein Schlüssel für Kommunikation mit dem Backend
* [authDomain](https://firebase.google.com/docs/reference/js/v8/firebase.auth.Config#optional-authdomain), eine Domain auf der Ihre Firebase Steuerelemente ("widgets" in Firebase Termini) gehostet werden
* projectId, die Identifikation (eindeutig) Ihres Projekts
* [storageBucket](https://firebase.google.com/docs/storage/admin/start?hl=de), ist ein Standard-Speicherplatz für Ihre App, der über die Verwaltung generiert wird
* [messagingSenderId](https://firebase.google.com/docs/cloud-messaging/js/receive?hl=de), ist eine Identifikatio, mit der Nachrichten an und von der App gesendet werden können
* appId, ist die Identifikation Ihrer App im Projekt
* [measurementId](https://firebase.google.com/docs/analytics/get-started?platform=web&hl=de#add_the_sdk_to_your_app), zu Analysezwecken

Damit Sie in der Anwendung die "Web-Namespace-API" verwenden können sind einige Anpassungen an Ihrer index.html notwendig.

Fügen Sie im head folgende Referenzen hinzu (damit kann der Namespace firebase erreicht werden):

``` html
<script src="https://www.gstatic.com/firebasejs/10.5.0/firebase-app-compat.js"></script>
<script src="https://www.gstatic.com/firebasejs/10.5.0/firebase-auth-compat.js"></script>
```

Fügen Sie dann **vor Ende des body-Elements folgendes script** ein und fügen dort die **Konfiguration aus Firebase** ein:

```html
<script type="module">
    
    // Konfiguration
    <!-- Konfiguration aus Firebase kommt hier statt des Kommentars hin!-->
    
    // Initialize Firebase
    firebase.initializeApp(firebaseConfig);
    
    // Ab hier kommen die weiteren Anwendungen von Firebase hin
    
</script>
```



[**Zurück zum Haupttutorial**](tutorial.md)