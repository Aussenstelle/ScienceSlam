# Architektur
- Server (Raspi)
- Bridge (Arduino mit WLAN)
  - Voll-Dynamische Adressvergabe
  - Brige Broadcasts MBN2EM Packets to Server (Raspi, Zentrale) imideatly
- Device (Arduino)


# Ideen / Notizen
  - `Dolmetsch`-Server, der TCP/IP in (z. B. Websockets) umwandelt

# Kommandos
- Senden
- Update
- Adressenbelegung
  - Kommando (von Server zu Gateway (ohne MBN2)): `00000100`
  - Server fragt Gateway nach belegten adressen
  - Gateway antwortet mit string von länge 255, 0 heißt kein gerät, 1 heißt belegt.
- Nachricht von Device
  - Server fragt mit Kommando `00000101` nach neuster Nachricht an das Gateway
  - Kommando (Antwort) (Von Gateway zu Server): `00000010`
  - Kommando + Adresse + Databytes werden an Server "Gedumpt" (Ohne charackter zwischen Bytes)
- Nachricht von Server an Device über Gateway
  - Kommando (Von Server zu Gateway): `00000011`
  - Kommando + Adresse + 8 Bytes direkt hintereinander, ohne character dazwischen.
