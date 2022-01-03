# Swift 



## Variablen

- let = wenn Variable sich verändern kann während der Laufzeit

- var = wenn Variable gleich bleibt

#### Variable und String ausgeben

```swift
let output = "Deine Domainname ist: \(benutzerInput)"
```



## Zuweisen von Werten

```swift
var x = 10
var y = 5
var z = y

if z == y { // == überprüft ob gleich
    print(z)
}
 var abc = 2
abc += 4 // abc = abc + 4 ner wert wird gleich zugewiesen
abc -= 1
```



### Increment++ und Dekrement--

- ++variable --> Wert erhgöt u dann ausgelesen
- variable++ variable ausgelesen und dann erhöht 



### Switch - Statement

Beuioeht sich auf den Weer

```swift
var tor = 3

switch tor {
case 1:
    print("Auto gewonne")
case 2:
    print("Küche gewonnen")
case 3:
    print("Zonk")
default:
    print("Unmbekannt")
}

var name = "Manu"

switch name {
case "Manu":
    print("\(name) hat Auto gewonne")
case "Alex":
    print("\(name) hat Küche gewonnen")
case "Felix":
    print("\(name) hat den Zonk gezogen")
default:
    print("\(name) Unmbekannt")
}
```



## Structs

- einfacher als Klassen, gibt keine Vererbung
- können aber auch eigene Typen erstellt werden
  - eingelteiter: ==struct Name {}==
- Es können auch Methoden und Properties festgelegt werden
- brauchen dafür keinen Initializer, weil hat memberinitialieser --> greift automatisch auf die members des Struct zu u initialisiert sie

``` swift

struct Rechteck {
    let breite: Int
    let hoehe: Int
}

let rechteck = Rechteck(breite: 10, hoehe: 20) // verlangt automatisch nach den properties

struct Quadrat {
    
    let breite: Int
    let hoehe: Int
    
    init(seitelaenge: Int) {
        breite = seitelaenge
        hoehe = seitelaenge
        // nun haben höhe u breite die gleiche seitenlänge
    }
    
    func seitenlaenge()-> Int {
        
        let ergebnis = breite + hoehe
        return ergebnis
    }
    
    func flaeche() -> Int {
        let ergebnios = breite * hoehe
        return ergebnios
    }
    
}

let quadrat = Quadrat(seitelaenge: 20)
print("Das Quadrat ist \(quadrat.hoehe) hoch und \(quadrat.breite) breit")
print("Die Seitenlänge des Quadrates ist :\(quadrat.seitenlaenge())")
print("Die Fläche des Quadrates ist: \(quadrat.flaeche())")
```

## Enumerations

- Sinde Wertetypen, heißt, eine Instanz wird beim Zuweisen kopiert

- Eigene sich super um zusammengehörige Werte zu gruppieren u in eigenen typ zu verpacken zb- Einheiten
  
  - Eingelteit: ==enum Name{}==
  
- meist zum erstellen von cases genutzt ==case Name u durch beistrich trennen==

- kann durch name der enum klasse und Punktnoration aufgerufen werden

  - ``` swift
    var aktuelleEinheit = Laengeneinheit.centimenter
    ```

- nach dem ersten Mal aufrufen reicht auch nur mit Punktnotation

  ```swift
  aktuelleEinheit = .kilometer		
  ```

- Der default wert muss nur gesetzt werden, wenn nicht alle Fälle berücksichtigt werden

``` swift
enum GewichtsEinheit {
    
    case gramm, kilogramm, tonne

}
var einheit = GewichtsEinheit.gramm
einheit = .kilogramm

switch einheit {
case .gramm:
    print("Die aktuelle Einheit  beträgt Gramm")
case .kilogramm:
    print("Die aktuelle Einheit ist Kilogramm")
case .tonne:
    print("Die aktuelle Einheit ist Tonne")
}

```

- rawValues und Assosiated Valus

  ```swift
  // rawValues und Associate Valuies
  // assosiated values helfen um enums später werte zuzuweisen
  enum Typ {
      case text(String)
      case nummer(Int)
  }
  
  let text = Typ.text("Hallo")
  let nummer = Typ.nummer(10)
  
  switch text {
  case .nummer(let wert):
      print(wert)
  case .text(let inhalt):
      print(inhalt)
  }
  
  //rawValues: kann nur ein typ für die ganze enum angegeben werden
  
  enum kommazahlen: Double {
      case eins = 1.0//jedem case muss jetzt ein rawValue zugewiesen werden
      case zwei = 2.0
      case drei = 3.0
  }
  let kommaZahl = kommazahlen.drei
  kommaZahl.rawValue
  
  enum Integer: Int {
      case eins, zwei, drei
  }
  
  let eins = Integer.eins.rawValue // hier bekomme ich als RawValue die 0, da swift von 0 zu zählen beginnt
  
  enum Faben: String {
      case rot, grün, blau
  }
  
  let grün = Faben.grün.rawValue // hioer wird dann der case von oben direkt zugeteilt, case wird als String für den rawvalue angenommen.
  //rawValues werden aber nur bei Integer und String automatisch verteilt
  //bei Interger könnten wir eine nStartwert angeben, von dem gezählt werden soll
  
  enum Intergere: Int {
      case fünf = 5, sechs, sieben
  }
  
  let fünf = Intergere.fünf.rawValue
  let sechs = Intergere.sechs.rawValue
  
  ```

  

## Optionals

- um variablen anzugeben, die eventuell keinen Wert haben
- mit ==?== hinter dem Typ der variablen definiert
- wenn wir auf eine leere Variable zugreifen, bekommen wir dann einen Fehler im Programm
- mit ==!== beim andwender der Variable gebe ich an, das der Wert entpackt werden soll- Wenn aber der Wert der Variable Leer ist, bekomme ich einen Error
- Optional chaining: mit einer if-Bedingugn wird untersucht, ob ein Wert vorhanden wird

```swift

struct Adresse {
    var strasse: String
    var hausnummer: Int
    var postleitzahl : Int
    var stadt: String
}

class Person {
    var name: String
    var adresse : Adresse? //
    
    
    init(name: String) {
        
        self.name = name
    }
}

let person1 = Person(name: "Manu")
// kann sein, das Person keine Adresse hat
//definieren dafür eine Variable Adresse in der Klasse Person die vom Typ Adresse aus dem struct ist

//print("\(person1) hat die Adresse \(person1.adresse!)") // kommt errror, da keine adresse vorhanden ist

if let adresse = person1.adresse {
    print("\(person1.name) hat die Adress \(adresse)")
} else {
    print("Die Adressse ist unbekannt")
}

//damit adresse vergeb wird muss ich eine instanz des struct definieren
let adresse = Adresse(strasse: "Prof franz Spath Ring", hausnummer: 21, postleitzahl: 8042, stadt: "Graz")
// und diese dann meienr person zuweisen
person1.adresse = adresse


if let adresse = person1.adresse {
    print("\(person1.name) hat die Adress \(adresse)")
} else {
    print("Die Adressse ist unbekannt")
}

```



## Pushnotifications





## DiesDas

cmd + shift + / = Zeile auskommentieren