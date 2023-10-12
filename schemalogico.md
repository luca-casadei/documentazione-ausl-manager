# Schema logico Pari o Dispari

## Entità principali

- UTENTE(<ins>Tessera</ins>,*CodiceScuola*,Cognome,Nome,DataNascita,Email,Password,CodiceFiscale)
- UTENTEAUSL(<ins>Email</ins>,Password)
- UTENTECUCINA(<ins>Username</ins>,Password,Email)
- MENU(<ins>Id</ins>,*EmailAusl*,Nome)
- PORTATA(<ins>Id</ins>,Note,Contenuto,Tipo)
- MENUTENTE(<ins>*TesseraUtente*</ins>,<ins>*IdMenu*</ins>,<ins>Numero</ins>,Stagione,Modificato);
- RICHIESTAMODIFICA(<ins>NumeroRichiesta</ins>,*Tessera*,*IdMenu*,*UtenteAusl*,Data,Approvato)
- SCUOLA(<ins>CodiceMeccanografico</ins>,*CodiceComunale*,Tipologia,Indirizzo,CAP,Denominazione)
- COMUNE(<ins>Codice</ins>,*CodiceProvinciale*,Nome)
- PROVINCIA(<ins>Codice</ins>,Nome,Sigla,*CodiceRegionale*)
- REGIONE(<ins>Codice</ins>,Nome)

## Relazioni

- ATTRIBUZIONEPORTATE(<ins>*IdMenu*</ins>,<ins>*IdPortata*</ins>)
- ATTRIBUZIONESCUOLACUOCHI(<ins>*CodiceScuola*</ins>,<ins>*UsernameUtenteCucina*</ins>)
- ASSOCIAZIONECUCINE(<ins>*UsernameCuoco*</ins>,<ins>*TesseraUtente*</ins>)

## FOREIGN KEYS
- UTENTE.CodiceScuola → SCUOLA
- MENU.EmailAusl → UTENTEAUSL
- MENUTENTE.TesseraUtente → UTENTE
- MENUTENTE.IdMenu → MENU
- RICHIESTAMODIFICA.Tessera → UTENTE
- RICHIESTAMODIFICA.IdMenu → MENU
- RICHIESTAMODIFICA.UtenteAusl → UTENTEAUSL
- SCUOLA.CodiceComunale → COMUNE
- COMUNE.CodiceProvinciale → PROVINCIA
- PROVINCIA.CodiceRegionale → REGIONE
- ATTRIBUZIONEPORTATE.IdMenu → MENU
- ATTRIBUZIONEPORTATE.IdPortata* → PORTATA
- ATTRIBUZIONESCUOLACUOCHI.CodiceScuola → SCUOLA
- ATTRIBUZIONESCUOLACUOCHI.UsernameUtenteCucina → UTENTECUCINA
- ASSOCIAZIONECUCINE.UsernameCuoco → UTENTECUCINA
- ASSOCIAZIONECUCINE.TesseraUtente → UTENTE