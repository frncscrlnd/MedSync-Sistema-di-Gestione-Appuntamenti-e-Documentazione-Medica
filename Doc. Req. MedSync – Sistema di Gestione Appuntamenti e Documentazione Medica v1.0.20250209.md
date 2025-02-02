## Stakeholders:
- pazienti: fruitori principali del servizio;
- medici: si affidano al sistema per agevolare il proprio lavoro;
- personale amministrativo: intermediario tra paziente e medico;
- sistema: permette una gestione efficiente delle attività;
- identity provider: permette un controllo rigido degli accessi.
## Requisiti funzionali:
### Registrazione: 
- i pazienti devono (MUST) potersi registrare al sistema attraverso [[#^id|Identità digitale]];
- i medici devono (MUST) potersi registrare al sistema attraverso [[#^id|Identità digitale]].
### Log-in:
- i pazienti devono (MUST) poter accedere attraverso [[#^id|Identità digitale]];
- i medici devono (MUST) poter accedere attraverso [[#^id|Identità digitale]].
### Gestione appuntamenti:
- i pazienti devono (MUST) poter prenotare un appuntamento;
- i pazienti devono (MUST) poter disdire un appuntamento;
- i medici devono (MUST) poter fornire il calendario di disponibilità agli appuntamenti;
- i medici devono (MUST) poter modificare il calendario di disponibilità agli appuntamenti;
- il personale amministrativo deve (MUST) poter disdire un appuntamento;
- il personale amministrativo deve (MUST) poter prenotare un appuntamento;
### Consultazione documenti:
- i pazienti devono (MUST) poter consultare la propria documentazione clinica;
- i pazienti devono (MUST) poter richiedere l'eliminazione definitiva dei propri dati;
- i medici devono (MUST) poter consultare le documentazioni cliniche dei pazienti che hanno in cura;
- i medici devono (MUST) poter aggiungere nuovi documenti clinici che riguardano i pazienti che hanno in cura;
- il personale amministrativo [[#^rbac|non deve (MUST (NOT)) avere accesso alle documentazioni cliniche dei pazienti]].
### Notifica automatica:
- i pazienti dovrebbero (SHOULD) poter ricevere notifiche relative ai propri appuntamenti;
- i medici dovrebbero (COULD) poter ricevere notifiche relative ai propri appuntamenti;
## Requisiti non funzionali:
### Sicurezza
- il sistema deve rispettare le norme del regolamento europeo per la protezione dei dati (GDPR) in termini di dati sensibili. Per farlo vengono prese alcune misure specifiche:
	- implementazione di un controllo rigido degli accessi attraverso un identity provider;^id
	- implementazione dell'approccio di sicurezza Role-Based Access Control (RBAC);^rbac
	- controllo dell'integrità comparando i digest di una funzione di hashing applicata alle documentazioni cliniche.