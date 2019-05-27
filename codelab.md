id: 0
author: Antonello Galipò and Gonçalo Palma
categories: apps, flutter
environments: web
status: draft

# BIVI - Biglietto da Visita, a Flutter Codelab

## Cosa è Flutter?
Duration 00:02

Flutter è blah blah blah

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

```
code to paste
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

```
code to paste
```

### La navigazione
La navigazione in Flutter puó essere vista come una pila di schermate (widget) della quale lo schermo visualizza la cima.
Ogni volta che navighiamo su una nuova schermata, la aggiungiamo alla cima della pila. Ogni volta che torniamo indietro, rimuoviamo dalla cima della pila la schermata che stiamo visualizzando in quel momento.

La navigazione è gestita da un componente specializzato chiamato Navigator.

Per navigare su una nuova schermata, effettuiamo il push di essa nello stack (pila) di navigazione in questo modo:

```
Nagigator.of(context).push(...);
```





### Write some code
``` dart
print("Hello world");
```

## Final step
You're done for the day!
