

# Ekosystem do streamowania

Poniższe funkcje pozwalają na implementację tych rozwiazań w kilku językach programowania


## Moduły WebStream

+ letJson
+ jsondef
+ jBodys
+ jLoads
+ jRoutes




## język programowania:

#### JavaScript
+ domena: js.[funkcja].com

#### PHP
+ domena: php.[funkcja].com

#### Python
+ domena: py.[funkcja].com



# Modularyzacja
[Modularyzacja przy wytwarzaniu oprogramowania.](https://www.hipermodularyzacja.pl/)

## Ogólne Dane

### Logo
+ logo.[funkcja].com

### Dokumentacja
+ docs.[funkcja].com


## per Moduł

### Pobranie, paczka
+ get.[język].[funkcja].com

### Edycja, repozytorium git
+ git.[język].[funkcja].com




## [let json](https://www.letjson.com)
![let json](https://logo.letjson.com/1/cover.png)



### Rozwiązania

pobieranie pliku json z URL możliwość kontroli procesu poprzez funkcję succes w przypadku poprawnego pobrania oraz error, gdy plik nie istnieje, lub nie ma odpowiedniego formatu

#### Osobne callback-i do pozytywnego i negatywnego przypadku

```php
letJson( String  url, Function  success, Function  error)
```

#### Metoda try - catch, bez callback, do error

```php
try{
    letJson( String  url, Function  json, Function  item)
}catch(){

}
```

### Przykłady użycia

#### 1. użycie z adresem url, callback: success, error

```js
letJson(
    "get.domain.com/file.json",
    function(name, value, json) {

    },
    function(error) {

    }
);
```

#### 2. użycie z adresem url, bez callback do error, ale throw exception

```js
letJson(
    "get.domain.com/file.json",
    function(json) {
        // zwraca całość pliku JSON
    },
    function(item) {
        // zwraca każdorazowo element lub parę klucz, wartość
    }
);
```

#### 3. użycie z adresem url, oddzielne parametry jako funkcje,

+ zwiększa przejrzystosć kodu,
+ pozwala na łatwą rozbudowę

##### asynchronicznie

```js
letJson(
    "get.domain.com/file.json"
).
json(
    function(json) {
        // zwraca całość pliku JSON
    }
).
item(
    function(item) {
        // zwraca każdorazowo element lub parę klucz, wartość
    }
);
```

##### synchronicznie

        var json = letJson("get.domain.com/file.json");



## [json def](https://www.jsondef.com)
![json def](https://logo.jsondef.com/2/cover.png)


okreslanie oczekiwanej struktury oraz podłączenie każdego elementu JSON pod konrketną funkcję

### def.json

```json
{
    "xpath/name":"function1",
    "xpath/name":"function1"
    "xpath/name":"function1"
}
```

### jsonDef(json, success, error)

```js
    jsonDef(
        "get.domain.com/def.json",
        function(name, value, json) {

        }
    );
```

### Pobranie definicji dla pliku JSON

```js
letJson(
    "get.domain.com/def.json",
    function(json) {
        letJson(
                "get.domain.com/file.json",
                function(name, value, json) {



                }
        )
   }
);
```





## [jBodys](https://www.jbodys.com)
![jBodys](https://logo.jbodys.com/2/cover.png)


+ jBodys()

Definicja moułu, poprzez określenie zalezności ładowania
W anstaepnej wersji również określanie wersji

```json
{
  "/form/field/text.css",
  "/form/field/email.css",
  "/form/field/submit.css",
  "newsletter.html": [
      "submit.js"
  ]
}
```

Wielopoziomiowe pobieranie plikó JSON
Budowanie struktury pliku JSON z wielu plików

```json
{
  "/form/field/submit.json": {
      "newsletter.json": [
          "submit.json",
          "/form/field/text.json",
          "/form/field/email.json",
      ]
  }
}
```

## [jLoads](https://www.jloads.com)
![jLoads](https://logo.jloads.com/2/cover.png)

+ jLoads()

Działanie na drzewie DOM, ładowanie stron do konrketnych tagów przy ładowaniu strony
Ładowanie konkretnych zasobów/mediów poprz ich adres url do formatu wyświetlanego w HTML bez okreslenia miejsca gdzie ma być załadowane,
pliki będą tylko definiowały same zależnosci:


## [jRoutes](https://www.jroutes.com)
![jRoutes](https://logo.jroutes.com/2/cover.png)


+ jRoutes()
pipelines (event, from, to) definicja miejsc, gdzie i co ma być z czym połączone z jLoads na HTML



## [jPaths](https://www.jpaths.com)
![jRoutes](https://logo.jpaths.com/2/cover.png)

+ jPaths()

routing dla url
+ praca z adresami url
+ event listener




## [jRuns](https://www.jruns.com)
![jRoutes](https://logo.jruns.com/2/cover.png)
+ jRuns()

devops part
+ deployment
+ monitoring


jRuns is an executor that allows you to execute builds on a remote machine by executing commands over SSH.
it's usefull to nodejs/deno environment as backend application

# Examples

![hypermodularity](hypermodularity.png)

## Tworzenie aplikacji offline poprzez karty (NFC)

![kids_cards](kids_cards.png)

It works online but You can create it offline, by NFC cards with your handy, without any application.

## Przykładowa aplikacja

Sczytujemy kolejno karty od góry do dołu poprzez czytnik NFC (poprzez smartfon'a) i kolejno są otwierane adresy, które są identyfikowane jako kolejne elementy (identyfikacja adresu IP), równocześnie powstaje strona www oparta o te moduły. Lista modułów jest zapisana w JSON, ładowane są za pomocą rozwiązania WebStream .dev , wcześniej biblioteka jLoads, teraz kilka modularnych funkcji docelowo na kilka jezyków, dzięki czemu nie będzie problemu z implementacją w python, php, itd

![modules](modules.png)



## About Webstream

+  Website about Webstreaming on github - [web-stream/www](https://github.com/web-stream/www)

## About Tom Sapletta

+ [Contact on linkedin](https://www.linkedin.com/in/tom-sapletta-com/)
+ [Tom Sapletta Blog - Embedded System Software & Hardware Developer](https://tom.sapletta.com/)
+ [Softreck Company - Leadership Through Software Development](https://softreck.com/)


## Devops supported by [Api Foundation](https://www.apifoundation.com)

+ [.apicra](https://www.apicra.com) - bash scripts to prepare environment
+ [.apifunc](https://www.apifunc.com) - funkcje, implementacja apiunit
+ [.apiunit](https://www.apiunit.com) - metadane potrzebne do stworzenia aplikacji
+ [.apibuild](https://www.apibuild.com) - budowanie plaikacji, deployment
+ [.apiterminal](https://www.apiterminal.com) - devops terminal by web


## Substantively supported by: 

+ [SaaS is King .com](https://www.saasisking.com/)
+ [hyper Modularity .com](https://www.hypermodularity.com/)


## Sponsored by:

+ [Softreck - Leadership Through Software Development](https://softreck.com/)



---
+ [edit](https://github.com/web-stream/modules/edit/main/README.md)
```
https://github.com/web-stream/modules.git
```

