# Troubleshoooting #

[**Zurück zum Haupttutorial**](tutorial.md)

## Konsolenfehler ##

### Failed to load resource: net::ERR_BLOCKED_BY_CLIENT ###

AdBlock, Ghostery oder ähnliche Erweiterungen in Browsern können die Ausführung verhindern. Deaktivieren Sie sie für Ihre Site.

## Funktionsfehler ##

### Anmeldung per Email und Passwort funktioniert nicht! ###

Firebase UI ist nicht kompatibel mit dem neuen [Email-Aufzählungsschutz](https://cloud.google.com/identity-platform/docs/admin/email-enumeration-protection?hl=de). [Diese Lösung](https://cloud.google.com/identity-platform/docs/admin/email-enumeration-protection?hl=de#disable) hilft hier.
Dieses Problem wurde erst vor kurzem gefunden und ist in der aktuellen FirebaseUI noch **nicht** **gelöst**. (_Anmerkung_: Registrierung und andere Funktionalitäten funktionieren jedoch.)

_

[**Zurück zum Haupttutorial**](tutorial.md)