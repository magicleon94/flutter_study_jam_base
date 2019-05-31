id: 0
author: Antonello Galipò and Gonçalo Montes Palma
categories: apps, flutter
environments: web
status: draft

# BIVI - Biglietto da Visita, a Flutter Codelab

## Cosa è Flutter?
Duration 00:02

Flutter è il nuovo framework made in Google per la realizzazione di UI in maniera semplice e veloce.
Il linguaggio di programmazione è Dart, anch'esso di casa Google.

Il framework permette di generare interfacce grafiche pixel-perfect via codice, con tutti i vantaggi che ne possono conseguire. Possiamo infatti sfruttare le proprietà dei linguaggi di programmazione a oggetti per realizzare delle UI robuste e pulite velocemente ed in maniera semplice.

Tra le qualità di Flutter spiccano:
- performance molto simili a quelle native, in quanto il codice viene compilato direttamente per il device, senza attraversare schiere di layer, gestendo tutto in autonomia, dal rendering alla logica
- linguaggio di programmazione semplice ed intuitivo, che risulta familiare sin da subito
- ampio catalogo di widget out of the box sia per lo stile Material che per lo stile di iOS
- semplicità di realizzazione di custom widget 
- hot reload, che permette di sincronizzare le modifiche al codice con il dispositivo in maniera quasi istantanea, applicandole direttamente preservando lo stato dell'app. In questo modo sarà possibile vedere in tempo reale le modifiche effettuate senza dover incorrere in fastidiosi riavvii dell'applicazione.
- totale controllo sulle animazioni

Questa tecnologia sta subendo una forte crescita, trovando sempre più TO BE CONTINUED

## Preparazione
Duration 00:20

Prima di iniziare sono necessarie due cose, [installare Flutter sul proprio computer](https://flutter.dev/docs/get-started/install) e [configurare un editor per utilizzarlo con Flutter](https://flutter.dev/docs/get-started/editor).

Una volta fatto ciò saremo in grado di scrivere applicazioni in Flutter e di eseguire su:
* dispositivi fisici 
* emulatore Android
* emulatore iOS

## Crea un nuovo progetto Flutter
Duration 00:05

A seconda dell'editor scelto, crea un nuovo progetto Flutter seguendo le istruzioni a [questo link](https://flutter.dev/docs/get-started/test-drive).

Chiama l'applicazione BIVI.

## Rimuovi il codice di esempio per un inizio pulito
Duration 00:02

Cancella tutto il codice contenuto in `lib/main.dart` ed incolla il seguente:

``` dart
import 'package:flutter/material.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      theme: ThemeData(
        primarySwatch: Colors.blue,
      ),
      home: MyHomePage(),
    );
  }
}

class MyHomePage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text("BIVI!"),
      ),
      body: Center(
        child: Text("Placeholder"),
      ),
    );
  }
}
```

## Creazione della pagina principale
Duration 01:30

In questa sezione creerai la pagina contenente la prima parte del biglietto da visita.

Utilizza i widget `Card`, `Container`, `Row`, `Column` e `Text`per realizzare un layout simile a quello in figura.
Ricorda:
- gli attributi `color`, `width` ed `height` di `Container`
- la dimensione di una `Card` è dettata dal `Container ` che la contiene
- gli attributi `MainAxisAlignment` e `CrossAxisAlignmenr` di `Row` e `Column`
- l'attributo `style` di `Text`

## Interattività e navigazione
Duration 01:00

### Il widget InkWell
InkWell è uno dei widget piú comuni per rendere interattivo un wigdet. 
Inserendo un widget come child di un InkWell, sarà infatti possibile specificare le azioni da compiere a fronte di un tap, doppio tap, long press, etc.

Le azioni da compiere a fronte di un evento di tocco sono descritte da funzioni di eseguire, che possono essere fornite al widget in uno dei seguenti modi:

``` dart
InkWell(
    onTap: () {
    print("tapped!");
    },
    onDoubleTap: () {
    print("double tapped!");
    },
    child: //Widget da rendere tappabile,
),
```

### La navigazione
La navigazione in Flutter puó essere vista come una pila di schermate (widget) della quale lo schermo visualizza la cima.
Ogni volta che navighiamo su una nuova schermata, la aggiungiamo alla cima della pila. Ogni volta che torniamo indietro, rimuoviamo dalla cima della pila la schermata che stiamo visualizzando in quel momento.

La navigazione è gestita da un componente specializzato chiamato Navigator.

Per navigare su una nuova schermata, un esempio di come effettuare il push di essa nello stack (pila) di navigazione in questo modo:

``` dart
Navigator.of(context)
.push(MaterialPageRoute(
    builder:(context){
        return NewPage();
    }),
);
```

Il codice riportato ottiene un riferimento all'istanza di `Navigator`
relativa al contesto attuale, e richiede il push di una nuova pagina,
costruita mediante il builder messo a disposizione dalla classe `MaterialPageRoute`.

### Rendere interattivo il biglietto da visita
È possibile combinare `InkWell` e le azioni col `Navigator` per aggiungere interattività 
e navigare su una seconda schermata, che al momento sarà vuota.

Per fare ciò:

1. Crea una nuova schermata aggiungendo in fondo a `main.dart` il seguente

``` dart
class MyBiography extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text("Antonello Galipò"),
        centerTitle: true,
      ),
      body: Container(
        color: Colors.red,
      ),
    );
  }
}
```

2. Rendi tappabile il biglietto da visita inserendolo in un `InkWell` ed usando `Navigator` in questo modo:
``` dart
Navigator.of(context)
.push(MaterialPageRoute(
    builder:(context){
        return MyBiography();
    }),
);
```

## Caricamento immagini dalla rete
Duration 00:05
In Flutter le immagini possono essere mostrate in diversi modi:
* `Image.asset(path)`
* `Image.memory(buffer)`
* `Image.network(url)`

La seconda pagina dell'app dovrà mostrare un'immagine recuperata da internet
ed una piccola descrizione.

Un esempio di immagine caricata da internet è il seguente:

```dart
Image.network(
  "https://prova.example.com"
);
```


## Completa la seconda schermata
Duration 00:15
Modifica il widget `MyBiography` includendo un'immagine dalla rete ed un testo in basso.

## Fine!
Se sei arrivato fin qui significa che hai finito tutto in tempo, grande!

Sentiti libero di sperimentare con altri widget dal [catalogo di Flutter](https://flutter.dev/docs/development/ui/widgets) e di chiedere al team eventuali dubbi!
