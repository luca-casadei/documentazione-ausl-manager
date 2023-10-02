# Schema logico per database
## Composizione dei menu
- INGREDIENTE(<ins>Id</ins>, Nome, Calorie)
- ALIMENTO(<ins>Id</ins>, Nome)
- COMPOSIZIONEALIMENTO(<ins>IdIngrediente*</ins>,<ins>IdAlimento*</ins>)
- PIATTO(<ins>Id</ins>, Nome)
- COMPOSIZIONEPIATTO(<ins>IdAlimento*</ins>, <ins>IdPiatto*</ins>)
- MENU(<ins>Id</ins>,Node, EmailUtenteAUSL*)
- COMPOSIZIONEMENU(<ins>IdPiatto*</ins>, <ins>IdMenu*</ins>)

## Utenti
- UTENTECUCINA(<ins>Username</ins>, Email, Password)
- BAMBINO(<ins>CodiceFiscale</ins>,DataNascita,Email,Password, Nome, Cognome)
- ASSOCIAZIONECUCINE(<ins>UsernameUtenteCucina*</ins>, <ins>CodiceFiscaleUtente*</ins>)
- UTENTEAUSL(<ins>Email</ins>, Password)
- RICHIESTAMODIFICA(<ins>CodiceFiscaleBambino*</ins>, <ins>IdMenu*</ins>,<ins>NumeroRichiesta</ins>, Data, Approvato, EmailUtenteAUSL*)
- MENUBAMBINO(<ins>IdMenu*</ins>,<ins>CodiceFiscale*</ins>, Stagione)

## Foreign keys
COMPOSIZIONEALIMENTO.IdIngrediente > INGREDIENTE
COMPOSIZIONEALIMENTO.IdAlimento > ALIMENTO
COMPOSIZIONEPIATTO.IdAlimento > ALIMENTO
COMPOSIZIONEPIATTO.IdPiatto > PIATTO
MENU.EmailUtenteAUSL > UTENTEAUSL
COMPOSIZIONEMENU.IdPiatto > PIATTO
COMPOSIZIONEMENU.IdMenu > MENU
ASSOCIAZIONECUCINE.UsernameUtenteCucina > UTENTECUCINA
ASSOCIAZIONECUCINE.CodiceFiscaleUtente > BAMBINO
RICHIESTAMODIFICA {CodiceFiscaleBambino, IdMenu} > MENUBAMBINO
RICHIESTAMODIFICA.EmailUtenteAUSL > UTENTEAUSL
MENUBAMBINO.CodiceFiscale > BAMBINO
MENUBAMBINO.IdMenu > MENU