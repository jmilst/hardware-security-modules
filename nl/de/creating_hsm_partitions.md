---

copyright:
  years: 2014, 2019
lastupdated: "2019-03-07"

keywords: hardware security modules, HSM, partitions, labels, cryptographic, keys,

subcollection: hardware-security-modules

---

{:shortdesc: .shortdesc}
{:external: target="_blank" .external}

# IBM Cloud HSM-Partitionen erstellen
{: #creating-ibm-cloud-hsm-partitions}

In einem {{site.data.keyword.cloud}} HSM (Hardwaresicherheitsmodul) müssen separate kryptografische Arbeitsbereiche initialisiert und für Clients designiert werden. Ein Arbeitsbereich - oder eine *Partition* - und alle zugehörigen Inhalte werden durch eine Verschlüsselung geschützt, die von der entsprechenden Authentifizierung abgeleitet ist. Nur ein Client, der die korrekte Authentifizierung angeben kann, darf die Partition anzeigen und mit dem Inhalt arbeiten.
{:shortdesc}

Bei der Erstellung der Partitionen muss beachtet werden, dass die Partitionsnamen, die auch Bezeichnungen genannt werden, im HSM eindeutig sein müssen. Es ist nicht möglich, zwei Partitionen mit derselben Bezeichnung in einem HSM zu erstellen. Der Name der Partition ist die Bezeichnung, die von PKCS #11-Anwendungen (Public-Key Cryptographic Standards) gelesen wird.

1. Melden Sie sich als HSM-Administrator mit dem Kennwort an, das für die Initialisierung des HSMs verwendet wurde.
```
[myLuna] lunash:>hsm login
HSM-Administratorkennwort eingeben.
>**************
HSM-Anmeldung erfolgreich.
Befehlsergebnis: 0 (Erfolg)
```
2. Partition erstellen.
```
[myLuna] Lunash:>partition create - partition customerPartionProd
Sicherstellen, dass Lizenzen für mindestens die folgende Anzahl an Partitionen erworben wurden: 1
Zum Fortsetzen des Vorgangs 'proceed' eingeben, andernfalls 'quit'.
> proceed
Verarbeitung läuft...
Ein Kennwort für die Partition eingeben:
>**************
Kennwort zur Bestätigung erneut eingeben:
>**************
Klondomäne für die Erstellung dieser Partition eingeben (Eingabetaste drücken, um die Standarddomäne zu verwenden):
> MyDomain
Erstellung der Partition erfolgreich.
Befehlsergebnis: 0 (Erfolg)
```
