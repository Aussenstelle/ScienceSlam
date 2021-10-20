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
  - Kommando (von Server zu Bridge (ohne MBN2)): `00000001`
  - Server fragt bridge nach belegten adressen
  - Bridge antwortet mit string von länge 255, 0 heißt kein gerät, 1 heißt belegt.
- Nachricht von Device
  - Kommando (Von Bridge zu Server): `00000010`
  - Adresse + Databytes werden an Server "Gedumpt" (Ohne charackter zwischen Bytes)
- Nachricht von Server an Device über Bridge
  - Kommando (Von Server zu Bridge): `00000011`
  - Adresse + 8 Bytes direkt hintereinander, ohne charackter dazwischen.
