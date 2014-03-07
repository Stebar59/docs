Come iniziare
=====

### Cosa c'è nella scatola

![Spark Core in box](images/core-in-box.jpg)

Congratulazioni per essere i nuovi proprietari di un nuovissimo Spark Core! Andate avanti, aprite la scatola e vediamo cosa trovate. La scatola dovrebbe contenere:

- *Uno Spark Core*. La ragione per cui ll'avete comperato. Andremo più in profondità fra poco.
- *Una breadboard*. La basetta sperimentale rende più semplice collegare i componenti al Core senza saldare. Internamente le righe lungo i bordi sono collegate orizontalmente mentre le colonne interne, verticalmente. Vedi  [l'articolo Breadboard su Wikipedia](http://it.wikipedia.org/wiki/Breadboard) per maggiori informazioni.
- *Un cavo USB*. Il cavo USB incluso è usato per due scopi: per alimentare lo Spark Core (collegandolo al vostro PC, ad un aimentatore USB o ad un pacco di batterie USB) e per riprogrammarlo. La maggior parte delle volte riprogrammerete il Core tramite il Cloud ma avrete sempre la possibilità di programmarlo via USB, specialmente se la connessione internet non è disponibile o se preferite usare i vostri server.


### Passo 1: Alimentare il Core

![Alimentare il Core](images/core-usb.jpg)

Alimentare il Core è facile; riceve corrente via una porta Micro USB come molti smartphone e altri apparecchi. Alimentate il vostro Core collegando il cavo Micro USB alla porta USB del Core e l'altra parte del cavo alla porta USB del vostro computer, ad un hub USB (preferibilmente con alimentazione) o ad un alimentatore USB (come quello che avete ricevuto col vostro smartphone).

Se desiderate, potete anche alimentare il Core con una sorgente da 3.6V fino a 6V collegata al pin `VIN`, o con 3.3V al pin `3.3V`.

### Passo 2: Scaricamento dell'applicazione Spark iOS o Android

![Spark apps](images/spark-apps.png)

L'applicazione Spark mobile è il modo più semplice per connettere il vostro Spark Core ad internet. L'applicazione vi aiuta a fare tre cose:

- Creare un account con Spark
- Connettere il vostro Spark Core alla vostra rete Wi-Fi
- Controllare il vostro Core senza scrivere una riga di codice

L'applicazione iOS necessita iOS 7, l'applicazione Android lavora con Ice Cream Sandwich (Android 4.0) e più recenti.

[Scarica l'applicazione iPhone >](https://itunes.apple.com/us/app/spark-core/id760157884)

[Scarica l'applicazione Android >](https://play.google.com/store/apps/details?id=io.spark.core.android)



### Passo 3: Collegare il Core alla rete Wi-Fi

![Smart Config](images/smart-config.png)

Connettere lo Spark Core al vostro Wi-Fi è molto semplice. Infatti, io l'ho fatto due volte scrivendo questo paragrafo!

L'applicazione Spark mobile vi guiderà in questo processo, ma praticamente è un solo passo dove dovrete inserire il nome della rete Wi-fi (SSID) e la password e questi verranno inviati via Wi-Fi allo Spark Core che, automaticamente, si collegherà alla rete e allo Spark Cloud. Se tutto funziona come deve, vedrete il LED passare da questi colori:

- **Blu lampeggiante**: in attesa delle credenziali del Wi-Fi
- **Verde lampeggiante**: in connessione alla rete Wi-Fi
- **Ciano lampeggianten**: in connessione allo Spark Cloud
- **Magenta lampeggiante**: aggiornamento al nuovo programma
- **Ciano pulsante**: Connesso!

<div id="core1" class="core"><div class="core-butt"></div><div class="rgb"><div class="pattern"></div></div></div>

<a id="button1" class="button" onclick="animateCore()">Vedi un'animazione</a>

Se l'applicazione mobile non va bene per voi, potete collegare lo Spark Core via USB. Per maggiori informazioni o per una spiegazione dettagliata su come collegare il Core alla rete, vedi:

[Collega il tuo Core >](/#/connect)

### Passo 4: Fare lampeggiare un LED con Tinker

![Tinker](images/tinker.png)

L'applicazione Spark mobile contiene una mini-applicazione chiamata Tinker che vi permette di ... appunto, tinker, cioè armeggiare. Vi permette di parlare con i pins di Input/Output dello Spark Core senza scrivere una singola riga di codice.

Ognuno dei pins ha quattro possibili funzioni: *digitalWrite*, *analogWrite*, *digitalRead*, e *analogRead*. Per maggiori informazioni, scorrere in basso alla sezione "Armeggiare con Tinker".

### Passo 5: Scrivere applicazioni con Spark Build

![Spark Build](images/ide.png)

Quando sarete stufi di leggere dati dai sensori e far lampeggiare dei LED, andate sulla Spark Build IDE per il vero spettacolo.  Spark Build vi permette di creare e caricare applicazioni personali sul vostro Core partendo da qualsiasi web browser moderno e di equipaggiare il vostro Core con tutte le possibilità di Internet!  Wow!  

Non siate nervosi--abbiamo preparato un sacco di applicazioni di esempio e di librerie approvate dalla comunità che vi permetteranno di partire col piede giusto. Per saperne di più, controllate la sezione "Scrivere applicazioni con Spark Build" più in basso in questa pagina.


Aspetta, cos'è questa cosa?
=====

Lo Spark Core è un kit di sviluppo Wi-Fi per hardware connesso ad internet. È il "cervello" di un progetto o prodotto connesso a internet.

Il Core contiene un microprocessore che è un piccolo computer, non costoso e a basso consumo che può eseguire un'applicazione unica. Il microprocessore fa lo show; esegue il tuo programma e dice al resto del Core cosa fare. Non ha un sistema operativo come il vostro computer; esegue solamente un'applicazione (spesso chiamata *firmware* o *embedded application*), che può essere semplice, di poche righe di codice o molto complessa, a seconda di quello che volete fare.

I microprocessori sono particolarmente bravi a *controllare cose*. Hanno diversi "pins" (delle piccole gambine che escono dal chip) che sono chiamate *GPIO* (General Purpose Input and Output) pins, o I/O pins. Possono essere collegati a sensori o bottoni per percepire il mondo, o collegati a luci e motori per interagire con esso. Questi pins del microprocessore sono stati direttamente collegati con i connettori sui lati del Core in modo da potervi accedere facilmente; specialmente i pins chiamati da D0 a D7 e da A0 a A7 sono direttamente collegati con i pins GPIO del microprocessore.

Il microprocessore può inoltre comunicare con altri chips usando protocolli standard, tipo *Serial* (anche chiamato UART), *SPI*, o *I2C* (anche chiamato Wire). Il Core può essere reso più performante connettendolo con dei chips con compiti speciali tipo driver per motori o shift registers. Ogni tanto questi chips sono integrati su un *Shield*, un acessorio del Core che permette di estendere il Core. 

Il Core ha inoltre un modulo Wi-Fi che lo connette alla vostra rete Wi-Fi locale nello stesso modo in cui il vostro computer o smartphone si connettono ad una rete Wi-Fi. Il Core è programmato in modo da restare sempre connesso ad internet per default, fintanto che trovi e possa connettersi ad una rete.

Quando il Core si connette a internet, stabilisce una connessione con lo *Spark Cloud*. Connettendosi con il Cloud, il Core diventa acessibile da qualsiasi luogo tramite una semplice REST API. Questa API è concepita per fare in modo che sia molto facile connettersi al Core tramite una applicazione web o mobile in modo sicuro e privato per far sì che solo voi e quelli di cui vi fidate possano accedere al Core.

### Bottoni

Ci sono due bottoni sul Core: il bottone RESET (sulla destra) e il bottone MODE (sulla sinistra). 

Con il bottone RESET si esegue un hard reset, proprio togliendo e rimettendo l'alimentazione al microprocessore. Questo è il modo migliore per far ripartire l'applicazione che avete caricato nel Core. Questo è il modo migliore per far ripartire l'applicazione che avete scaricato sul Core.

Il bottone MODE serve ha tre funzioni:

- Tenendo premuto il bottone MODE per tre secondi il Core entra in modalità *Smart Config* per connetterlo alla vostra rete Wi-Fi locale. Il LED dovrebbe cominciare a lampeggiare blu.
- Tenere premuto il bottone MODE per dieci secondi permette di cancellare la memoria delle reti Wi-Fi del Core.
- Tenendo premuto il bottone MODE e premendo una volta il bottone RESET e aspettando per *tre secondi* il Core entra in modalità *Bootloader*, dove potete riprogrammare il Core via USB o JTAG. Lasciare il bottone quando il LED lampeggia giallo. Se avete fatto tutto questo per errore, semplicemente premere il bottone RESET per lasciare la modalità *Bootloader*.
- Tenendo premuto il bottone MODE e premendo una volta il bottone RESET e aspettando per *dieci secondi* si effettua un *Factory Reset*, dove il Core viene riprogrammato con il software caricato in fabbrica (l'applicazione Tinker). Il LED dovrebbe diventare bianco per tre secondi e poi lampeggiare velocemente; quando il LED cambia su un altro colore il Core è stato inizializzato. Questa operazione è utile se avete problemi col il vostro firmware o se semplicemente volete tornare a Tinker.


### LEDs

Ci sono due LEDs sul Core. Quello più grande in mezzo è un LED RGB che fa vedere lo stato della connessione internet del Core. L'altro piccolo LED blu è il LED *LED utente*; è collegato al pin D7 e quindi quando impostate D7 a `HIGH` o `LOW`, si accende, rispettivamente si spegne.

Il LED RGB può indicare i seguenti stati:

- *Blu lampeggiante*: Modo in ascolto, in attesa delle informazioni della rete.
- *Blu fisso*: Smart Config completata, informazioni di rete trovate.
- *Verde lampeggiante*: In connessione con la rete locale Wi-Fi.
- *Ciano lampeggianten*: In connessione allo Spark Cloud.
- *Ciano pulsante*: Connesso con successo allo Spark Cloud.
- *Giallo lampeggiante*: Modo Bootloader, in attesa del nuovo codice via USB o JTAG.
- *Bianco lampeggiante*: Factory Reset inizializzato.
- *Bianco fisso*: Factory Reset completato; riavvio.

Il LED RGB serve anche ad indicare se ci sono stati errori durante la connessione a internet. *Il LED rosso indica un errore.* Gli errori possono includere:

- *Due flash rossi*: Errore di connessione dovuto ad una non buona connessione internet. Controllare la connessione internet.
- *Tre flash rossi*: Il Cloud non è accessibile ma la connessione internet è buona. Controllare il nostro [Feed Twitter](http://www.twitter.com/sparkdevices) per vedere se ci sono annunciati dei problemi; se non ci sono visitare la [pagina di supporto](https://www.sparkdevices.com/support) per ricevere aiuto.
- *Quattro flash rossi*: Il Cloud è stato raggiunto ma lo scambio di informazioni di sicurezza è fallito. Visitate la nostra [pagina di supporto](https://www.sparkdevices.com/support) per ricevere aiuto.
- *Lampeggio giallo/rosso*: Credenziali non valide per lo Spark Cloud. Contattare lo Spark Tteam (<a href="mailto@hello@spark.io">hello@spark.io</a>).

### Pins

Il Core ha 24 pins a cui si può collegare un circuito. Questi pins sono:

- _VIN_: Collegate qui un'alimentazione non regolata tra 3.6V e 6V per alimentare il Core. Se si alimenta il Core via USB, questo pin *non* deve essere usato.
- _3V3_: Questo pin fornisce una tensione regolata di 3.3V che può essere usata per alimentare delle componenti esterne al Core (Se avete la vostra alimentazione regolata di 3.3V la potete collegare qui per alimentare il Core).
- _3V3*_: Questa è una alimentazione regolata a basso disturbo di 3.3V da usare per circuiti analogici che potrebbero essere sensibili ai disturbi delle componenti digitali. Se usate dei sensori analogici sensibili alimentateli dal pin _3V3*_ invece che dal _3V3_.
- _!RST_: Potete inizializzare il Core (come premendo il tasto RESET) connettendo questo pin a massa (GND).
- _GND_: Questi pins sono collegati a massa.
- _D0 a D7_: Questi sono il pane e il burro dello Spark Core: 8 GPIO (General Purpose Input/Output) pins. Sono indicati con "D" perchè sono pins digitali, cioè non possono leggere i valori di sensori analogici. Alcuni di questi mettono a disposizione delle periferiche aggiuntive (SPI, JTAG, etc.), vedi più avanti per maggiori informazioni.
- _A0 a A7_: Questi pins sono 8 GPIO in più che portano il totale a 16. Questi pins sono come quelli da D0 a D7, ma sono "Analogici", cioè possono leggere i dati dai sensori analogici (tecnicamente hanno una periferica ADC). Come per i pins digitali anche questi hanno delle periferiche aggiuntive.
- _TX and RX_: Questi pins sono per la comunicazione via seriale/UART. TX rappresenta il pin di trasmissione e RX quello di ricezione.

#### Pins PWM

Quando volete usare la funzione `analogWrite()` nel Core, per esempio per regolare la luminosità di LEDs, dovete usare dei pins che hanno una periferica con timer. Questi pins vengono generalmente chiamati pins PWM perchè quello che fanno è chiamata Pulse Width Modulation.  Il Core ha 8 pins PWM: A0, A1, A4, A5, A6, A7, D0 e D1.

Lo Spark Cloud
---

Lo Spark Cloud è una rete di servers presso `https://api.spark.io/` dove il vostro Core si collega quando è collegato a internet.

Il Cloud esiste per tre ragioni principali:

### Semplicità

Parlando in generale, quando si lavora in un sistema incorporato (embedded system) networking significa inviare bytes tramite sockets TCP e datagrams UDP. Sono tutti daccordo che la programmazione UDP non è divertente. La comunicazione a livelli più alti è difficile perchè i microprocessori hanno così poca memoria che non possono generalmente ospitare un server web HTTP tradizionale. Il Cloud vi da la semplicità del server web con i costi e la potenza ridotti di un microprocessore facendo da tramite tra la comunicazione web (richieste HTTP) e quella incorporata (embedded), nel nostro caso messaggi CoAP criptati).

Ma non è necessario sapere tutto questo. Il bello del Cloud è che tutto questo è astratto. Non dovete sapere *come* il Core si connette ad internet; semplicemente lo fa. E una volta che è connesso gli potete far fare cose grandiose velocemente e facilmente, senza occuparvi di sockets.

### Disponibilità globale

Per default, se connettete qualcosa alla vostra rete Wi-Fi, questa è accessibile solamente internamente alla rete locale. Questo è dovuto al fatto che si è a corto di indirizzi IP ed è anche una misura di sicurezza, visto che ciò non permette a persone qualsiasi di accedere alla vostra rete ed immischiarsi nei fatti vostri.

Rendere disponibile le vostre cose al di fuori della rete locale non è evidente e normalmente richiede operazioni speciali tipo mapping delle porte e indirizzi IP statici. Anche se siete tecnicamente preparati per maneggiare tutto ciò, se sviluppate un prodotto non volete che essere ferrati con OpenWRT sia un presupposto per l'acquisto di esso.

Evitiamo tutto questo con il Cloud. Il Core si connette con il Cloud appena è sulla vostra rete Wi-Fi e mantiene una connessione con esso sempre aperta. Questo significa che è raggiungibile sempre e da ogni parte del mondo.

Ma un momento, se le reti locali sono una misura di sicurezza, questo non vi espone a ogni sorte di problemi? Beh, certo potrebbe ma ...

### Sicurezza

Sì, esatto. Ci abbiamo pensato!

La sicurezza è difficile. Specialmente in un sistema embedded visto che il criptaggio è molto affamato di risorse. Ma è anche molto importante perchè non volete certo che qualcuno accenda e spenga le vostre luci, o peggio ancora, che apra e chiuda le vostre porte.

Abbiamo selezionato una serie di protocolli di sicurezza molto solidi che sono sicuri ed efficenti in modo da funzionare bene in un sistema embedded. Sono integrati nel protocollo Spark, che è open source e pronto per essere esteso ad altri prodotti.


Armeggiare con "Tinker"
======
L'applicazione Tinker
---

![Tinker](images/tinker.png)

La sezione Tinker dell'applicazione Spark mobile rende molto semplice cominciare a giocare con lo Spark Core senza bisogno di scrivere del codice. È l'ideale per l'inizio dello sviluppo e spesso potrà fare tutto il necessario per far partire il vostro progetto.

L'applicazione consiste in 16 pins in colonne verticali - 8 pins analogici sulla sinistra, 8 pins digitali sulla destra. Questi pins rappresentano i 16 pins GPIO (General Purpose Input and Output) dello Spark Core e sono organizzati nello stesso modo.

![Tinker selection](images/tinker-select.png)

Per cominciare tocca uno dei pins. Apparirà un menu con le funzioni a disposizione. Ogni pin può avere quattro funzioni:

- **digitalWrite**: Mette il pin a HIGH o LOW, connettendolo a 3.3V (la tensione massima del sistema) rispettivamente a GND (massa).Il pin D7 è collegato al LED interno; set mettete il pin D7 a HIGH, il LED si accende mentre se lo mettete a LOW, si spegne.
- **analogWrite**: Mette il pin ad un valore tra 0 e 255, dove 0 è come LOW e 255 come HIGH. Questo è come inviare una tensione tra 0 e 3.3V sul pin, ma essendo il sistema digitale, viene usato un meccaniscmo chiamato Pulse Width Modulation, o PWM. Per esempio potete usare *analogWrite* per cambiare l'intensità ad un LED.
- **digitalRead**: Questo legge il valore digitale del pin, che può essere HIGH o LOW. Se avete collegato il pin a 3.3V, la lettura sarà HIGH; se lo connettete a massa (GND) sarà LOW. Per valori intermedi la lettura sarà il valore più vicino ma pericolosamente non ben definito.
- **analogRead**: Questa funzione legge il valore analogico di un pin, che è un valore tra 0 e 4095 dove 0 è LOW (GND) e 4095 è HIGH (3.3V). Tutti i pin analogici (da A0 a A7) possono usare questa funzione. *analogRead* è l'ideale per leggere i dati dai sensori.

Per cambiare la funzione semplicemente rimanere sul pin e riapparirà il menu per la selezione delle funzioni. Avete altre domande? Contattateci sui [forums!](https://community.sparkdevices.com/)

Il firmware Tinker
---

Il firmware Tinker é l'applicazione che viene installata di partenza sullo Spark Core quando esce dalla linea di produzione della fabbrica. Potete sempre tornare a questa applicazione mettendo il Core nel modo [factory reset](#bottoni), o ricaricando il Core con Tinker nell'applicazione Spark mobile.

L'applicazione Tinker è un bel esempio di come creare un'applicazione potente senza troppo codice. Potete dare un'occhiata all'ultima versione [qui.](https://github.com/spark/core-firmware/blob/master/src/application.cpp)

La API Tinker
---

When the Tinker firmware is installed on your Spark Core, it will respond to certain API requests from your mobile app, which mirror the four basic GPIO functions (digitalWrite, analogWrite, digitalRead, analogRead). These API requests can also be made from another application, so you can build your own web or mobile app around the Tinker firmware.

### digitalWrite

Sets the pin to HIGH or LOW, which either connects it to 3.3V (the maximum voltage of the system) or to GND (ground). Pin D7 is connected to an on-board LED; if you set pin D7 to HIGH, the LED will turn on, and if you set it to LOW, it will turn off.

    POST /v1/devices/{DEVICE_ID}/digitalwrite

    # EXAMPLE REQUEST IN TERMINAL
    # Core ID is 0123456789abcdef01234567
    # Your access token is 1234123412341234123412341234123412341234
    curl https://api.spark.io/v1/devices/0123456789abcdef01234567/digitalwrite \
      -d access_token=1234123412341234123412341234123412341234 -d params=D0,HIGH

The parameters must be the pin (A0 to A7, D0 to D7), followed by either HIGH or LOW, separated by a comma. The return value will be 1 if the write succeeds, and -1 if it fails.



### analogWrite

Sets the pin to a value between 0 and 255, where 0 is the same as LOW and 255 is the same as HIGH. This is sort of like sending a voltage between 0 and 3.3V, but since this is a digital system, it uses a mechanism called Pulse Width Modulation, or PWM. You could use *analogWrite* to dim an LED, as an example.

    POST /v1/devices/{DEVICE_ID}/analogwrite

    # EXAMPLE REQUEST IN TERMINAL
    # Core ID is 0123456789abcdef01234567
    # Your access token is 1234123412341234123412341234123412341234
    curl https://api.spark.io/v1/devices/0123456789abcdef01234567/analogwrite \
      -d access_token=1234123412341234123412341234123412341234 -d params=A0,215

The parameters must be the pin (A0 to A7, D0 to D7), followed by an integer value from 0 to 255, separated by a comma. The return value will be 1 if the write succeeds, and -1 if it fails.

    


### digitalRead

This will read the digital value of a pin, which can be read as either HIGH or LOW. If you were to connect the pin to 3.3V, it would read HIGH; if you connect it to GND, it would read LOW. Anywhere in between, it'll probably read whichever one it's closer to, but it gets dicey in the middle.

    POST /v1/devices/{DEVICE_ID}/digitalread

    # EXAMPLE REQUEST IN TERMINAL
    # Core ID is 0123456789abcdef01234567
    # Your access token is 1234123412341234123412341234123412341234
    curl https://api.spark.io/v1/devices/0123456789abcdef01234567/digitalread \
      -d access_token=1234123412341234123412341234123412341234 -d params=D0


The parameter must be the pin (A0 to A7, D0 to D7). The return value will be 1 if the pin is HIGH, 0 if the pin is LOW, and -1 if the read fails.



### analogRead

This will read the analog value of a pin, which is a value from 0 to 4095, where 0 is LOW (GND) and 4095 is HIGH (3.3V). All of the analog pins (A0 to A7) can handle this. *analogRead* is great for reading data from sensors.

    POST /v1/devices/{DEVICE_ID}/analogread

    # EXAMPLE REQUEST IN TERMINAL
    # Core ID is 0123456789abcdef01234567
    # Your access token is 1234123412341234123412341234123412341234
    curl https://api.spark.io/v1/devices/0123456789abcdef01234567/analogread \
      -d access_token=1234123412341234123412341234123412341234 -d params=A0

The parameters must be the pin (A0 to A7, D0 to D7). The return value will be between 0 and 4095 if the read succeeds, and -1 if it fails.


Flash Apps with Spark Build
===

What is firmware?
---

An *embedded system* like the Spark Core doesn't have an Operating System like a traditional computer. Instead, it runs a single application, often called *firmware*, which runs whenever the system is powered.

*Firmware* is so-called because it's harder than software and softer than hardware. Hardware is fixed during manufacturing, and doesn't change. Software can be updated anytime, so it's very flexible. Firmware is somewhere in between; hardware companies do issue firmware updates, but they tend to be very infrequent, because upgrading firmware can be difficult.

In our case, because the Spark Core is connected to the internet, updating firmware is quite trivial; we send it over the network, and we have put in place safeguards to keep you from "bricking" the Core.

When you flash code onto the Spark Core, you are doing an *over-the-air firmware update*. This firmware update overwrites almost all of the software on the Spark Core; the only piece that is untouched is the bootloader, which manages the process of loading new firmware and ensures you can always update the firmware over USB or through a factory reset.  (We'll be open sourcing the bootloader as soon as we can bring the README up to date.)

Logging into Spark Build
---
When you're ready to reprogram your Spark Core, head over to our IDE:

[Spark Build >](https://www.spark.io/build)

![Spark Build](images/create-account.jpg)

Creating an account is a simple one-step process.  When presented with the login screen, simply enter your email address (careful!), and desired account password.  Press the big friendly "Sign Up" button, and you'll reach the Spark Build home page.

![Spark Build](images/log-in.jpg)

If you've already logged into Spark Build before, click the "Let me log in" text beneath the Sign Up button, and you'll be presented with a login for existing users.  Don't worry--if you already have an account and accidentally click the "Sign Up" button, we'll still log you into your existing account.

Spark Build, our web IDE
---

![Spark Build](images/ide.png)

Spark Build is an Integrated Development Environment, or IDE; that means that you can do software development in an easy-to-use application, which just so happens to run in your web browser.

Spark Build starts with the navigation bar on the left. On the top, there are three buttons, which serve important functions:

- **Flash**: Flashes the current code to the Spark Core. This initiates an *over-the-air firmware update* and loads the new software onto your Spark Core.
- **Verify**: This compiles your code without actually flashing it to the Core; if there are any errors in your code, they will be shown in the debug console on the bottom of the screen.
- **Save**: Saves any changes you've made to your code.

At the bottom, there are four more buttons to navigate through the IDE:

- **Code**: Shows a list of your firmware applications and lets you select which one to edit/flash.
- **Docs**: Brings you to the documentation for Spark.
- **Cores**: Shows a list of your Spark Cores, so you can choose which to flash, and get more information on each Core.
- **Settings**: Change your password, log out, or get your access token for API calls.

Spark Apps and Libraries
---

![Spark Build](images/spark-apps.jpg)

The heart of Spark Build is the "Spark Apps" section, which displays the name of the current app in your editor, as well as a list of your other applications and community-supported example apps.

The application you've got open in the editor is displayed under the "Current App" header.  You'll notice that this "HELLOWORLD" sample application has only one file, but firmware with associated libraries/multiple files are fully supported.  

From this pane, you've got a lot of buttons and actions available to you that can help you grow and manage your library of kick-ass applications:

- **Create**: You can create a new application by clicking the "Create New App" button.  Give it a sweet name and press enter!  Your app is now saved to your account and ready for editing.

- **Delete**: Click the "Remove App" button to remove it forever from your Spark library.

- **Rename**: You can rename your Spark App by simply double-clicking on the title of your app under the "Current App" header.  You can modify the "Optional description" field in the same way.
- **My Apps**: Tired of working on your current project?  Select the name of another app under the "My apps" header to open it in a tab of the Spark Build editor.

- **Files**: This header lists all known files associated with the open application.  Click on a supporting file in your application to open it as an active tab in the editor.

- **Examples**: The "Example apps" header lists a continuously growing number of community-supported example apps.  Use these apps as references for developing your own, or fork them outright to extend their functionality.


Flashing Your First App
---

The best way to get started with the IDE is to start writing code:

- **Connect**: Make sure your Core is powered and "breathing" Cyan, which indicates that it's connected to the Spark Cloud and ready to be updated.

---
- **Get Code**: Try clicking on the "Blink an LED" example under the "Example apps" header.  The Spark Build editor should display the code for the example application in an active tab.  Alternatively, you can copy and paste this snippet of code into a new application in the Build IDE.

```
//D7 LED Flash Example
int LED = D7;

void setup() {
   	pinMode(LED, OUTPUT);
}

void loop() {
   	digitalWrite(LED, HIGH);
   	delay(1000);
   	digitalWrite(LED, LOW);
   	delay(1000);
}
```

![Spark Build](images/select-a-core.jpg)

- **Select Your Core**: The next step is to make sure that you've selected which of your Cores to flash code to.  Click on the "Cores" icon at the bottom left side of the navigation pane, and click on the start next to the Core you'd like to update.  Once you've selecte a Core, the star associated with it will turn yellow.

- **Flash**: Click the "Flash" button, and your code will be sent wirelessly to your Core.  If the flash was successful, the LED on your Core will begin flashing magenta.

![Spark Build](images/fork-app.jpg)

- **Fork**: Wish the timing of that LED flash was a little bit faster?  Try clicking on the "Fork This Example" button after selecting the "Blink An LED" example application.  You've now got a personal copy of that application that you can modify, save, and flash to all of your Cores.

- **Edit**: Try changing the values in the delay() function from 1000 to 250, which changes the timing interval from 1000 milliseconds to only 250 milliseconds.  Click the Verify button, then the Flash button.  Is your Core's LED blinking faster?  Well done :)


Account Information
---

There are a couple of other neat bells and whistles in Spark Build.  The Spark Build IDE the best tool for viewing important information about your Core, managing Cores associated with your Spark account, and "unclaiming" them so they can be transferred to your buddy.

![Spark Build](images/device-id.jpg)

- **Core ID**: You can view your Core's Device ID by clicking on the "Cores" icon at the bottom of the navigation pane, then clicking the dropdown arrow next to the Core of interest.  

- **Unclaim**: You can "Unclaim" a Core by pressing the "Remove Core" button that is revealed by clicking the dropdown arrow.  Once a Core has been unclaimed, it is available to be reassociated with any Spark users' account.

![Spark Build](images/access-token.png)

- **API Key**: You can find your most recent API Key listed under the "Settings" tab in your account.  You can press the "Reset Token" button to assign a new API Key to your account.  *Note* that pressing this button will require you to update any hard-coded API Credentials in your Spark-powered projects!






The Spark Command Line
===

**Coming soon!** Command line tools so that you can build Spark applications with your own desktop IDE, whether it's Eclipse, Sublime Text, Vim, or anything else.

Deploying a Spark web app
===

**Coming soon!** We'll give you instructions for how to deploy a web app on Heroku that can talk with a Spark Core.

Troubleshooting
===

What's wrong?
---

### My Core won't connect to Wi-Fi

There are many reasons that your Core might not be connecting to your Wi-Fi network. To debug, check out our detailed connection troubleshooting section:

[Why won't it connect? >](/#/connect/troubleshooting)

### I can't talk to my Core

Once your Core is connected, it needs to be *claimed* in order to be associated with your account. This is what lets you control your Core and keeps anyone else from doing so.

If you use the mobile app to set up your Core, it should claim it automatically. However if you connect your Core over USB, or if the claiming process is unsuccessful, you can claim it manually.

Head over to our connection page to learn about this:

[ Claiming your Core >](/#/connect/claiming-your-core)

### My Core won't start up

If your Core won't start up (the LED never comes on), here are a few things to check:

- Is the Core receiving sufficient power? If you're not sure, connect a multimeter to the 3.3V pin and GND and see if you get 3.3V, as expected. Try connecting the Core to another power source.
- Have any components been damaged? Visually inspect both sides of the Core.

### My Core is behaving erratically

If you're seeing unexpected behavior with your Core, here are a few things to check:

- Is the Core receiving sufficient power? The Core might behave eratically if it's plugged into an unpowered USB hub and not receiving enough power. In addition, if you have components that draw a lot of power (motors, for instance), you might need more power than your computer can supply. Try using a USB power supply or providing more power directly to the VIN or 3.3V pins.
- If you have a u.FL Core, is an antenna connected? Are you within range of the Wi-Fi router?


Further resources
===

Hardware development
---

### Hardware for dummies

**Coming soon!**

### Advanced hardware

**Coming soon!**

Software development
---

### Software for dummies

**Coming soon!**

### Advanced software

**Coming soon!**
