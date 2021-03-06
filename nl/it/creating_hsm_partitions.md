---

copyright:
  years: 2014, 2019
lastupdated: "2019-03-07"

keywords: hardware security modules, HSM, partitions, labels, cryptographic, keys,

subcollection: hardware-security-modules

---

{:shortdesc: .shortdesc}
{:external: target="_blank" .external}

# Creazione delle partizioni di IBM Cloud HSM
{: #creating-ibm-cloud-hsm-partitions}

All'interno di un HSM (Hardware Security Module) {{site.data.keyword.cloud}}, devono essere avviati e progettati spazi di lavoro crittografici separati per i client. Uno spazio di lavoro o *partizione* e tutti i suoi contenuti sono protetti dalla codifica derivante dalla sua autenticazione. Solo a un client che presenta l'autenticazione appropriata viene consentito di visualizzare la partizione e di utilizzarne i contenuti.
{:shortdesc}

Quando crei le tue partizioni, assicurati che i nomi della partizione, conosciuti anche come etichette, devono essere univoci nell'HSM. Non puoi creare due partizioni con la stessa etichetta in un HSM. Il nome che fornisci alla tua partizione è l'etichetta visualizzata dalle applicazioni PKCS (Public-Key Cryptographic Standards) #11.

1. Accedi come un amministratore HSM con la password utilizzata per avviare l'HSM.
```
[myLuna] lunash:>hsm login
Please enter HSM Administrators' password:
>**************
hsm login successful.
Command Result : 0 (Success)
```
2. Crea la partizione.
```
[myLuna] Lunash:>partition create - partition customerPartionProd
Please ensure that you have purchased licenses for at least this number of partitions: 1
If you are sure to continue then type proceed, otherwise type quit.
> proceed
Processing...
Please enter a password for the partition
>**************
Please re-enter password to confirm:
>**************
Please enter the cloning domain to use when creating this partition (press enter to use the default domain):
> MyDomain
partition create successful
Command Result : 0 (Success)
```
