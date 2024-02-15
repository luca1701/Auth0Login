# Auth0Login
L'applicazione _Auth0Login_ mostra l'implementazione di un sistema con servizio di autenticazione <b>Auth0</b>.
<br>
Auth0 è una piattaforma di gestione dell'identità e dell'accesso che fornisce servizi di autenticazione e autorizzazione per applicazioni web, mobili e API.
Auth0 è basato su OAuth2.0 che è un protocollo di autorizzazione utilizzato per consentire a un'applicazione di ottenere l'accesso limitato a risorse su un altro servizio, senza la necessità di condividere le credenziali degli utenti.
***
# Cos'è Auth0?
<b>Auth0</b> permette di:
- aggiungere diverse sorgenti per l'autenticazione come <b>Google, Facebook, Microsoft Account, LinkedIn, GitHub, Twitter, Box, Salesforce, among others, or enterprise identity systems like Windows Azure AD, Google Apps, Active Directory, ADFS or any SAML Identity Provider.</b>
- aggiungere un sistema di autenticazione tradizionale basato su username e password, mediante uso di db.
- generare Json Web Tokens per la chiamata di specifiche API e per il controllo di flusso dell'identità degli utenti.
- informaazioni aggiuntive su come, dove e quando gli utenti si loggano.

# Configurazione applicazione per l'uso di Auth0
Primo passo è la creazione di un account su [Auth0](https://auth0.com/signup), per poi usare lo stesso per la creazione dell'applicazione.

Di seguito una schermata della dashboard principale
![alt text](image-8.png)

<br><br>
***
<br><br>

Una volta creata sarà necessario prendere nota degli identificativi relativi a <b>Domain, Client-ID</b>, presenti tra le impostazioni della stessa.
![alt text](image-10.png)

>Tali parametri individuati saranno poi da sostituire nello script _environments.ts_, rispetto ai nomi in maiuscolo. YOUR_REDIRECT_URI sarà invece relativo all'indirizzo cui volete l'applicazione si ridirezioni una volta effettuato il login tramite auth0.
```
{
export const environment = {
  production: false,
  auth0: {
    domain: 'YOUR_DOMAIN ',
    clientId: 'YOUR_CLIENT_ID',
    redirectUri: 'YOUR_REDIRECT_URI',
  },
};
}
```

***

Di seguito, alcune schermate dell'applicazione. Dalla dashboard principale sino alla schermata del profilo, contenente __email__, __nickname__ e __immagine del profilo__.
![alt text](image.png)
![alt text](image-1.png)
![alt text](image-3.png)
![alt text](image-4.png)
![alt text](image-5.png)
![alt text](image-6.png)
![alt text](image-7.png)
![alt text](image-11.png)

# Esecuzione
Per l'esecuzione dell'applicazione, dopo aver completato la parte di configurazione, basterà:
- posizionarsi mediante terminale nella cartella del progetto scaricato
- lanciare il comando per l'installazione di Angular, se non presente, io ho usato la v. 14.0.2 quindi _npm install -g @angular/cli@14.0.2_ . Se non specificata verrà scaricata in automatico l'ultima versione.
- lanciare il comando _npm install_ per l'installazione di tutti i pacchetti necessari all'esecuzione
- lancio del comando _ng serve_ per eseguire l'applicazione in locale(solitamente viene usata la porta 4200, se occupata sarà possibile cambiarla col comando _ng serve --port 4201_)