# [Authentifizierung](https://firebase.google.com/docs/auth?hl=de) über Firebase #

[**Zurück zum Haupttutorial**](tutorial.md)

## Firebase Authentication ##

Gehen Sie über das Seitenmenü zum Modul "**Authentication**" und klicken Sie auf "Los gehts". Damit initialisieren Sie die Einrichtung.  

![firebase20_auth.png](pix%2Ffirebase20_auth.png)

Wählen Sie als erste Authentifizierungsmethode **"E-Mail-Adresse/Passwort"**:

![firebase21_auth.png](pix%2Ffirebase21_auth.png)

Hier müssen Sie diese Funktionalität nur mehr **per Slider aktivieren**.

![firebase22_auth.png](pix%2Ffirebase22_auth.png)

Danach sehen Sie den **Überblick** Ihrer Authentifizierungsmethoden. Wählen Sie einen neuen, zusätzlichen Anbieter! 

![firebase23_auth.png](pix%2Ffirebase23_auth.png)

Wählen Sie "Google". Damit können Sie sich auch **mit einem Google-Konto auf Ihrer App** authentifizieren. (Info zu [OAuth2](https://oauth.net/2/) und [Verwendung in Google](https://developers.google.com/identity/protocols/oauth2?hl=de))

![firebase24_auth.png](pix%2Ffirebase24_auth.png)

Aktivieren Sie die Möglichkeit. Ihre **Mailadresse(n) in Ihrem Google-Konto** stehen zur Auswahl für **Supportanfragen**.

![firebase25_auth.png](pix%2Ffirebase25_auth.png)

Danach stehen 2 "Anbieter" in der Authentifizierung unter "**Sign-In method"**.

![firebase26_auth.png](pix%2Ffirebase26_auth.png)

Weitere Einstellungen sind möglich. Zum Beispiel können Sie die **Vorlagen** (mit Einschränkungen) der automatisierten Mails ändern. Des Weiteren könnten Sie statt dem **[SMTP](https://de.wikipedia.org/wiki/Simple_Mail_Transfer_Protocol) Service** von Google auch Ihren eigenen verwenden.

![firebase27_auth.png](pix%2Ffirebase27_auth.png)

**Registrierte Benutzer** finden Sie zu Beginn des Dialogs unter dem Reiter "**Users**". Hier können Sie auch selbst neue Benutzer eingeben!

![firebase28_auth.png](pix%2Ffirebase28_auth.png)

[**Zurück zum Haupttutorial**](tutorial.md)



## [WebApp Implementierung](https://firebase.google.com/docs/auth/web/firebaseui?hl=de&authuser=0) ##

Firebase bietet Unterstützung über ein eigenes **User-Interface (UI)**, welches man einbinden muss. Dazu bindet man folgenden Code **im head von [index.html](../public/index.html) nach den anderen Firebase Bibliotheken** ein (_Anmerkung_: __de im Dateinamen lädt die lokalisierte deutsche Version):

``` html
<script src="https://www.gstatic.com/firebasejs/ui/6.0.1/firebase-ui-auth__de.js"></script>
<link type="text/css" rel="stylesheet" href="https://www.gstatic.com/firebasejs/ui/6.0.1/firebase-ui-auth.css" />
```

Im body kann das **UI in ein div-Element gerendert** werden. Fügen Sie folgende HTML Code im body ein:

``` html
<div id="firebaseui-auth-container"></div>
```


Die **Initialisierung der UI** erfolgt im script-Bereich über 

``` javascript
var ui = new firebaseui.auth.AuthUI(firebase.auth());
```

Nun müssen die **Anmeldemethoden**, die in Firebase aktiviert wurden **in der UI konfiguriert** werden:

```javascript
var uiConfig = {
  signInOptions: [
    firebase.auth.EmailAuthProvider.PROVIDER_ID,
    firebase.auth.GoogleAuthProvider.PROVIDER_ID,  
  ],
};
```

Erweitern Sie die Variable **uiConfig** mit **Callbacks von der UI Komponente**. 

``` signInSuccessWithAuthResult```, mit welchem die erfolgreiche Anmeldung abgefangen werden kann. Der Rückgabewert gibt an, ob ein Redirect mit dem Parameter ```signInSuccessUrl``` geschieht (```return true;```) oder nicht (```return false;```)

```javascript
callbacks: {
    signInSuccessWithAuthResult: function (authResult, redirectUrl) {
        console.log("User logged in successfully!");
        return false;
    }
},
signInFlow: 'popup',
signInSuccessUrl: 'not-existing.html'
```

Abschließend wird die UI Komponente in das div-Element gerendert:

```javascript
ui.start('#firebaseui-auth-container', uiConfig);
```

![firebase29_auth.png](pix%2Ffirebase29_auth.png)

**_<span style="color:red">Problem</span>_**: 
Firebase UI ist nicht kompatibel mit dem neuen [Email-Aufzählungsschutz](https://cloud.google.com/identity-platform/docs/admin/email-enumeration-protection?hl=de). [Diese Lösung](https://cloud.google.com/identity-platform/docs/admin/email-enumeration-protection?hl=de#disable) hilft hier. 
Dieses Problem wurde erst vor kurzem gefunden und ist in der aktuellen FirebaseUI noch **nicht** **gelöst**. (_Anmerkung_: Registrierung und andere Funktionalitäten funktionieren jedoch.)

Zum **Anmelden** verwenden Sie daher bitte die 2. Methode **über Ihr Google-Konto**! Sie sollten die Meldung ```User logged in successfully!``` in Ihrer JavaScript Konsole sehen.

## Aufgabe ##

**Bauen Sie Ihre Anmeldung aus**, indem Sie das ```authResult``` im Callback abfangen und eine Funktion ```handleSignedInUser``` dafür implementieren 

```javascript
if (authResult.user) {
    handleSignedInUser(authResult.user);
}
```

Hier ein Ausschnitt vom **Ergebnis der erfolgreichen Anmeldung**:

![firebase32_auth.png](pix%2Ffirebase32_auth.png)

Wenn **das Objekt ```user``` existiert**, dann schreiben Sie eine Meldung wie zum Beispiel ...

![firebase30_auth.png](pix%2Ffirebase30_auth.png)

und **wenn nicht** ...

![firebase31_auth.png](pix%2Ffirebase31_auth.png)

[**Zurück zum Haupttutorial**](tutorial.md)