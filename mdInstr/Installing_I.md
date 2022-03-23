# GLI INSTALL DI LARAVEL

> GUIDA TUTTI I COMANDI DA USARE IN ORDINE PER PREPARARE UN FILE LARAVEL BACK/FRONT-OFFICE (COMPRESI FEATURE EXTRA)

## 1- installazione e creazione repo da terminale
<details><summary></summary>

```
composer create-project --prefer-dist laravel/laravel:^7.0 titolo-repo
```

</details>

## 2- prima installazione di npm e tutto lo scaffolding di scss
<details><summary></summary>

```
npm install
```

In teoria con queste due installazioni si è in grado di sfruttare laravel nel proprio file php, ma ci sono feature extra che permettono di sfruttare framework o strumenti/documentazioni utili a migliorare il proprio progetto.
</details>

## 3- installare Fontawesome in laravel
<details><summary></summary>

Si parte dal terminale usando il comando di installazione:
```
npm install --save @fortawesome/fontawesome-free
```
una volta fatto ciò, si importa il pacchetto di fontawesome nel file css, di preciso nel _```resource/sass/app.scss```_ la seguente sintassi:
```
@import'~@fortawesome/fontawesome-free/css/all.css';
```
</details>

## 4- installare DBAL
<details><summary></summary>

c'è una casistica particolare (ma comunissima) in cui è necessario modificare la struttura delle tabelle di un database, e per farlo non basa la semplice _```migration```_: nella terminale infatti, si dovrà installare il seguente comando da permettere migration di ogni necessità.
```
composer require doctrine/dbal:2.*
```
</details>

## 5- Faker per data-testing
<details><summary></summary>

sempre nell'ottica di testare e verificare il funzionamento del proprio database, di preciso di una tabella, sfruttare seeder e inserire manualmente miriade di dati risulta sconveniente; Faker corre in aiuto nel inventarsi in un proprio sistema randomico nomi, città, numeri e qualsiasi altra informazione possiamo immaginare. Però laravel tiene già installaro un faker tutto suo la _```fzaninotto/faker```_.
quindi converrà disinstallarla per installare _```fakerphp/faker```_ ovvero quello che necessitiamo noi.
```
composer remove fzaninotto/faker
composer require fakerphp/faker
```
</details>


## 6- UI ed autenticazioni
<details><summary></summary>

crearsi ed idearsi tutto un sistema di autenticazioni suona impossibile, ma per nostra fortuna Laravel UI ci viene in soccorso con un suo e utile scaffolding che installa anche bootstrap e vue.js.
Prima di tutto si installa UI della versione adatta alla versione di Laravel: 
```
composer require laravel/ui:^2.4
```
per installare la libreria e permettere l'auto scaffolding:
```
php artisan ui vue --auth
```
</details>


## 7- Bootstrap 5
<details><summary></summary>

avendo installato con _```npm install```_ e _```ui vue --auth```_, si ha boostrap con una versione (che oserei dire) parecchio datata.
quindi la fila di comandi da terminale per permettere il perfetto funzionamento di Boostrap 5 sono:
```
npm install bootstrap@5
npm install @popperjs/core
npm remove jquery
npm remove popper.js
```
ricordarsi di modificare in _```resources/js/bootstrap.js```_ con l'inserimento di 
```
Popper ->  
window.Popper = require('@popperjs/core').default;
```
e commentando/cancellando
```
jquery ->
window.$ = window.jQuery = require('jquery');
```
**RICORDATI CHE LE CLASSI SONO DA MODIFICARE PER BOOTSTRAP 4 A 5!**
</details>

