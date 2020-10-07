                        															Kotlin





Funktionen werden mit "fun" initialisiert: 

- fun main(args: Array<String>) { } / fun main() {}

Variablen: 

- "var" wird verwendet, wenn eine Variable veränderbar sein soll. --> var alter = 22
- "val" wird verwendet, wenn ein Variable !!nicht!! Veränderbar sein soll --> val name = "Manuel"
- Augegeben wird die Variable im println mit einem $vorDerVariable
- Durch var geburtsjahr : Int  --> lässt sich um Vorfeld eine Variable definieren

Print Funktion = println("Ich brauche kein Semicolon am Schluss") 

fn+control+r = automatischer Build

Mimo:

println("Hello world")

var greeting = "Bonjour"/ var greeting : **String** = "Bonjour"

val name = "Manuel"

```kotlin
var favourite = "Flash"
favourite = "Aquaman"
val length = favourite.lenght
println(length)
favourite = "Wonder Woman"
        print(favourite)

var shoutmouse = "Mouse"
shoutmouse =+ "!"
println(shoutmouse)
// mit .trim() bekommt man de nabstandt weg
// mit ${variable} kann man code in den Output einbauen
// wenn wir das $ Zeichen als $ Zeichen benutzen wollen, verwenden wir \$ (escape character)

var output = "She said \"I love coding\", after building her first app."
println(output)

Output: She said "I love coding", after building her first app.
```

var stunden = 16.15 --> double

```Kotlin
var score = 5
score = score +1
score ++
score += 10
```

```Kotlin
 var x = 3 + 14 - 11
    var y = 6
    var result = x == y
    println(result)
}
```

```kotlin
var truth = !true
println(truth) // false
```

```kotlin
var result2 = 1000 != 100
println(result2) // true
```

```kotlin
var z = true and false
println(z)
```

```kotlin
var h = true or false
println(h)
```

```kotlin
var a = "babelfish"
var b = "Babelfish"

println(a == b) // false
```



If-Bedingung:

```kotlin
var condiotion = true
if(condiotion) {
    println(5*4)
} else if (!condition) {
  println(3*8)
} else {
  println(5*9)
}
```

- ```kotlin
  var sonneScheint : Boolean = true
   var temperatur = 10
  
   if (temperatur < 0 && sonneScheint) {
       println("Happy day!")
   } else {
       println("Doofes Wetter...")
   }
  
   var sprache = "Kotlin"
  
   if (sprache == "Java"){
       println("Die Sprache ist Java")
   } else {
       println("Die Sprache ist Kotlin")
   }
  ```

```
var x2 = true
var y2 = false

if (x2 or y2) {

    println("Woho")
}
```



```kotlin
//Rechnenen

var radius = 6
val pi = 3.14159
var derUmfang = radius * pi * 2

println(derUmfang)

var geldbeutel = 40

geldbeutel -= 5

geldbeutel += 100

println(geldbeutel)

println("In 40 Jahren bin ich $alter")
```

```kotlin
//Lists and Arrays
  // 2 Möglichkeiten um Listen anzulegen:
    var helden = listOf<String>("Spiderman","Ironman","Batman","Captain Amerika")

    var schurken = listOf("Dr. Doom","Magneto","Joker","Ridler","Dr. Oktopus")

// add funktion geht nicht, da Listen nicht mutable sind, Liste kann also nicht erweitert werden

    println(helden.first())
    println(schurken.last())

    //veränderbare Listen:

    var weitereHelden = mutableListOf<String>("Flash","Falcon","Hulk","Hawkeye")

    println(weitereHelden)

    weitereHelden.add("Kid Flash")

    println(weitereHelden)

    //Arrays

    var primzhlen = arrayOf(2,3,5,7,11,13,17,23,29,31,37)

    println(primzhlen.get(4))


    var lieblingsfileme = listOf<String>("Matrix","Amazing Spiderman","End Game","Spiderman-multi Verse")

    println(lieblingsfileme)
```



```kotlin
//Arrays

var primzhlen = arrayOf(2,3,5,7,11,13,17,23,29,31,37)

println(primzhlen.get(4))

var lieblingsfileme = listOf<String>("Matrix","Amazing Spiderman","End Game","Spiderman-multi Verse")

println(lieblingsfileme)

val numbers = arrayListOf<Int>()//leeres Array
numbers.add(1)

var animals = arrayListOf<String>("cat","dog","mouse","bird")
var size = animals.size
animals[2] = "Rabbit"// eintrag ändern
animals.removeAt[0]// eintrag löschen
animals.add("")
println(size)

val lastElement = animals[size - 1]
println(lastElement)

val cat = animals.get(0)
var dog = animals[1]

println(cat)
println(dog)

animals.set(3,"dingo") // Einträge verändern
animals[4] = "penguin"

animals.add("horse") // Eintrag hinzufügen

 


//Schleifen

repeat(4){
        println("Time for Loop")
    } // printed 4x

for (i in 1..20){
    println(i)
}

var esssen = listOf<String>("Pizza","Schoko","Kebap","Schnitzel")

for (speise in esssen){

    println(speise)
}

for (i in 5..10){
    println(i)
}

for (zahl in 10..30  ) {
    if (zahl % 2 == 1) { //teile die zahl durch 2 gib mir den rest u wenn der restgleich 1 ist ist die bedingung erfüllt
        println(zahl)
    }
}

var livesLeft = 2

    while (livesLeft >= 0){
        println("Noch $livesLeft Leben übrig")
        livesLeft -=1

    }
    println("Game Over" )

//while

var index = 0

    while (index < 5) {
        index +=1
        println(index
        )
    }
```

```kotlin
//Maps

var mapsInSprachen = mutableMapOf<String, String>("Java" to "HashMap","Swift" to "Dictionary","Kotlin" to "HashMaps")
var wortUndZahl = mapOf("Millenium" to 2000, "Geburt Jesus" to 0)
println(mapsInSprachen["Java"])
println(mapsInSprachen)
mapsInSprachen ["Kotlin"] = "Maps"
println(mapsInSprachen)
mapsInSprachen.put("Hallo","Tacho")
println(mapsInSprachen)

var freundeUndAlter = mapOf<String, Int>("Kai" to 23,"Fabio" to 25,"Loz" to 27)

println(freundeUndAlter)
```



```kotlin
//Funktionen

fun printMessage(text: String){
  println(text)
}

fun giveMeFive(): Int {
        return 5
    }
    val output = giveMeFive()
    println(output)

printMessage("Bulding functions is fun")

 fun getTwoTimes(number: Int): Int {
        return 2 * number
    }
     val output2 = getTwoTimes(4
     )
    println(output2)

fun begruessen(wer: String, wen: String): String{
    return "$wer sagt hallo zu $wen"
}

println(begruessen("Manu","Kai"))

//ohne Rückgabewert
fun hallo() : Unit {
    println("hallo")
}

fun hallo2() :Unit = println("Hallo die 2te")

println(hallo())

//ohne geschweifte Klammern
fun nummernaddieren(num1: Int, num2: Int) : Int = num1 + num2
println(nummernaddieren(5,8))

//auch der Rückgabetyp kann weggelassen werden
fun nummernSubdrahieren(num1: Int, num2: Int)  = num1 - num2
var ergebniss = nummernSubdrahieren(10,3)
println(ergebniss)

fun nummernMulti(zahl1: Int, zahl2: Int) = zahl1 * zahl2
println(nummernMulti(3,8))

fun hund(name: String, alter: Int) = "Mein Hund heißt $name und ist $alter Jahre alt"
println(hund("Lessi",4))
```

```kotlin
/Klassen
//Variablen können direkt initialisiert werden
class Hund (var name:String, var alter:Int, var fellfabe: String) { // ist gleichzeitig primary Konstruktor

    fun altern(){
        alter += 1
    }

    fun hundeInfo() {
        println("$name ist $alter jahre alt und hat sein Fell ist $fellfabe" )
    }
}

class Person {
    
    var name: String = ""
    var age: Int = 0
}
//in anderer Klasse
val james = Person()
james.name = "James"
println("Name: #{james.name}")
println(james.age) // age aufrufen
class OtherPerson(var age: Int = 0){} //Komplette Class definiert

class SecondPerson(var name:String=""){}
val manuel = SecondPerson("Manuel")
println("Name: ${manuel,name}")

//functionen aufrufen
class Person{
  fun sayHello() {
    println("Hello!")
  }
}
val bob = Person()//In anderer Class
bob.sayHello()

class Person(var name:String = ""){
  fun sayHi(){
    println("Hi! I'am ${name}!")
  }
  var bob = Person("bon")//inanderen class
  bob.sayHi()
}

class thirthPerson(var isEating: Boolean = false){
    fun startEating() {
        isEating = true
        println("Nom, nom, nom")
    }
}
 var bobby = thirthPerson()//in anderen classe
    bobby.startEating()
    println("Is eating? ${bobby.isEating}")


class fourthPerson(var name: String = ""){
    fun setName(f:String, l:String){
        this.name = f + " " + l
    }
}
var ricky = fourthPerson()//in anderer class
//oder gleich so:
val ricky = 
Person("Ricky","Bobby")

    ricky.setName("Ricks","Bobby")
    println("Name: ${ricky.name}")





class Katze {
    var name: String
    var alter: Int

    //normaler Konstruktor
    constructor(name:String, alter:Int) {

        this.name = name
        this.alter = alter
    }

    //Konstrutor der nur eine Variable nimmt, Klasse kan mehere Konstruktoren haben
    constructor(name:String){
        this.name = name
        alter = 0
    }


   /* init {
        this.name = name
        this.alter = alter
    }*/

/*   Unterscheid zwischen Konstruktor und Initialisieren:
*
*
*
* */

   fun katzenInfo() {
       println("$name ist $alter Jahre alt")

   }


}

    fun main() {

        var meinHund = Hund("Lessi",4,"Braun")
        var meineKatze = Katze("Mia")
        var meine2teKatze = Katze("Koko",2)

        println(meinHund.alter)
        meinHund.altern()
        println(meinHund.alter)

        meineKatze.katzenInfo()
        meine2teKatze.katzenInfo()

        meinHund.hundeInfo()


    }
```



```kotlin
/*Nullable(optinals in Swift)
* Bedeutet eine Variable kann einene wert haben,
* kann aber auch leer sein
* */


fun main() {

    var a : String = "Hallo"
   // a = null --> nicht möglich

//Machmal ist aber auch wichtig, das eine Variable Leer ist#

    var b: String? = "hallo"
    b = null
    b = "hello again"


    //abfragen ob etwas in b drinnen ist, wenn ja, dann ausgeben, wenn nein dann nicht ausgeben


    if (b != null) {
        println("")
    } else {
        println("b $b ist Leer")
    }

    //länge der Variable ausgeben
    println(a.length)

    if (b != null){

        println(b!!.length) // braucht if abfrage wenn Variable mit ? deklariert ist, wenn sicher das nicht null !!
    } else {
        println("B ist wiederleer")
    }

    

}
```

### lateinit:

- private val lateinit
  - wenn schon am anfang klar ist, das die Variable erst später initialisiert wird



Java und Kotlin 



Java Code in Kotlin umwandeln : Auf MAinActivity --> Code --> Cover Java to Kotlin 

Nachfolgende Javacodes werden dann automatisch übersetzt. 

