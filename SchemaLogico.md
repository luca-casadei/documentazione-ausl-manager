# Schema logico per database
## Composizione dei menu
- INGREDIENTE(<ins>Id</ins>, Nome, Calorie)
- ALIMENTO(<ins>Id</ins>, Nome)
- COMPOSIZIONEALIMENTO(<ins>IdIngrediente*</ins>,<ins>IdAlimento*</ins>)
- PIATTO(<ins>Id</ins>, Nome)
- COMPOSIZIONEPIATTO(<ins>IdAlimento*</ins>, <ins>IdPiatto*</ins>)
- UTENTECUCINA(<ins>Username</ins>, Email, Password)
- UTENTE(<ins>CodiceFiscale</ins>, Nome, Cognome, Email, Password, IdMenu*)
- ASSOCIAZIONECUCINE(<ins>UsernameUtenteCucina*</ins>, <ins>CodiceFiscaleUtente*</ins>)
- UTENTEAUSL(<ins>Email</ins>, Password)
- MENU(<ins>Id</ins>, EmailUtenteAUSL*)
- COMPOSIZIONEMENU(<ins>IdPiatto*</ins>, <ins>IdMenu*</ins>)
- RICHIESTAMODIFICA(<ins>CodiceFiscaleUtente*</ins>, <ins>IdMenu*</ins>, Data, Approvato, EmailUtenteAUSL*)
