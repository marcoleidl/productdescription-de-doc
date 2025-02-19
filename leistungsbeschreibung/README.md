---
slug: /product-description/germany/leistungsbeschreibung
title: Leistungsbeschreibung
---

# fiskaltrust.Leistungsbeschreibung

Als Softwarehersteller entwickelt fiskaltrust Produkte für KassenHersteller und KassenHändler im Bereich Compliance-as-a-Service und Revisionssichere-Daten-as-a-Service. Die KassenHersteller und KassenHändler setzen daraufhin die fiskaltrust Produkte als Teil Ihrer eigenen Lösung beim KassenBetreiber ein.

## Compliance-as-a-Service

Als KassenHersteller erhalten Sie Compliance-as-a-Service, indem Sie die fiskaltrust.Middleware in Ihr Produkt integrieren. Durch die Übermittlung der Belegdaten, Transaktionen und anderer relevanten Daten an die fiskaltrust.Middleware wird Konformität als Service bereitgestellt. 

Die fiskaltrust.Middleware stellt eine länderübergreifende Schnittstelle zur Verfügung, die über verschiedene Kommunikationsarten (WCF, REST, gRPC, Serial-stream oder TCP-stream protocol) für Ihr Kassensystem erreichbar ist.

![Überblick über die Funktionsweise von fiskaltrust](../product-service-description/compliance-as-a-service/media/overview-pos-ft-middleware.png)                                

Die fiskaltrust.Middleware wird zu einem wesentlichen Bestandteil Ihres Kassensystems und gewährleistet damit die Konformität als Kassen- oder Aufzeichnungssystem. Sie erzeugt eine eindeutige, fortlaufende Identifikationsnummer eines von der Kasse übermittelten Request und stellt somit nachvollziehbar dar, dass jeder Request von ihr verarbeitet wurde.

Die Konformität wird durch die Kombination diverser Methoden und Komponenten erreicht.

Zunächst wird über die fiskaltrust.Middleware sichergestellt, dass die relevanten Daten von einer dritten Partei (fiskaltrust) neben dem KassenHersteller und dem KassenHändler verarbeitet werden. Dies nennen wir die organisatorische Implementierung des Schutzes vor Manipulation.

Zur technischen Implementierung des Schutzes vor Manipulation wird aus jedem Request von dem Kassensystem und auch von jedem dazugehörigen Response der fiskaltrust.Middleware ein Hash-Wert erzeugt. Dadurch wird die Datenintegrität der Requests und Responses sichergestellt. Um nachweisen zu können, dass keine Manipulation stattgefunden hat, wird ein weiterer Hash-Wert erzeugt, der sich auf den gesamten Request-Response-Zyklus bezieht (siehe auch Bild). Dieser Hash-Wert wird aus folgenden Angaben generiert:
- der eindeutigen Identifikation dieses Zyklus (RequestJournalId)
- dem Erstellungszeitpunkt (Moment)
- der Identifikationsnummer des Request (RequestIdentification)
- der Hash-Werte des Request und Response  (ReceiptRequestHash und ReceiptResponseHash)
- sowohl als auch dem Hash-Wert des vorherigen Zyklus. (ReceiptHash #n-1)

Diese Verkettung bietet unabhängig von der Verwendung einer TSE bereits die Möglichkeit, Manipulationen sicher zu erkennen.

 ![receipt-chain](../product-service-description/compliance-as-a-service/media/receipt-chain.png)


Um das Risiko einer Manipulation der Kette auf den letzten nicht verketteten Hash-Wert zu begrenzen, stellt fiskaltrust einen Mechanismus bereit, der die aktuellen Daten in die fiskaltrust.Cloud hochlädt und dadurch spiegelt. Diese Datenspiegelung ermöglicht es, Manipulationen zu erkennen, die an dem Kassen- oder Aufzeichnungssystem selbst nicht erkennbar wären.

Als weitere Komponente des fiskaltrust.SecurityMechanism stellt die fiskaltrust.Middleware marktbezogene Sicherheitsmechanismen zur Verfügung. In Deutschland wird zum Beispiel die TSE (Technische Sicherheitseinrichtung) über die SCU (Security Creation Unit) der fiskaltrust.Middleware angebunden.

Um für verschiedene Plattformen und Betriebssysteme zur Verfügung zu stehen und um das Versprechen zu erfüllen, als einheitliche Schnittstelle zum Kassen- oder Aufzeichnungssystem zu fungieren, ist die fiskaltrust.Middleware nach folgender Architektur aufgebaut.

  ![cashbox](../product-service-description/compliance-as-a-service/media/cashbox.png)


Der durch die CashBoxId identifizierte Konfigurationscontainer (CashBox) kann in verschiedene Plattformen und Betriebssysteme integriert werden. Die Erstellung und Verwaltung der Konfiguration inklusive der dazugehörigen Komponenten erfolgt im marktbezogenen fiskaltrust.Portal. Der fiskaltrust.SecurityMechanism wird von der Queue-Komponente und der SCU-Komponente (Signaturerstellungseinheit) bereitgestellt. Die SCU-Komponente stellt die Anbindung an den marktbezogenen Sicherheitsmechanismus (z.B. TSE) dar.


# Revisionssichere Daten-as-a-Service

Kassenbetreiber erhalten revisionssichere Daten-as-a-Service, indem sie ein Kassen- oder Aufzeichnungssystem verwenden, das die fiskaltrust.Middleware integriert hat. 

## fiskaltrust.Cloud

Die fiskaltrust.Middleware, spiegelt die Daten als Teil des fiskaltrust.SecurityMechanism in die fiskaltrust.Cloud. Die Datenintegrität wird durch den Hash-Wert der Requests und Responses sichergestellt, und die Vollständigkeit kann durch Nachverfolgung der Hash-Kette überprüft werden (s.o.). Diese Datenspiegelung stellt sicher, dass alle Originaldatensätze erhalten bleiben und nicht verändert werden. Auch der Schutz vor Verlust der gesamten Daten wird durch unsere Lösung durch standortverteilte Daten-Speicherung gewährleistet. Die Daten werden entsprechend der gesetzlichen Vorgaben in deutschen Rechenzentren gespeichert.

## POS Archiv

Das POS Archiv speichert die von der fiskaltrust.Middleware übergebenen Daten über einen Zeitraum von 12 Jahren. Über das fiskaltrust.Portal kann auf die Daten zugegriffen werden.

Bei Erstellen eines Monatsabschuss wird eine Prüfung zur Konsistenz der Daten durchgeführt und eine zusätzliche Exportdatei erstellt, die ebenfalls in der fiskaltrust.Cloud gespeichert wird.

[PDF Download der Leistungsbeschreibung](media/leistungsbeschreibung.pdf)
