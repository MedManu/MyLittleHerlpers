function sum (a: **number**, b: **number**): **number** { // Variablen müssen zahlen sein und return muss auch eine Zahl sein

​    return a + b

}

<h2> Typen:



- boolean - true or false
- number - just a number
- string - just a string
- Array - [1,2,3]
- tuple: - [string, numb, numb] 
  - let arr: [string, numb, numb] =["Hallo", 1, 2]
- enum - Outcum{Win. Lose, Draw}
- any - Dynamic type
- void - a function that doesn't return
- null - something doesn't exist
- undefined - unassigned variable
- never - function that never returns
- object - non-primitive typs

https://www.typescriptlang.org/docs/handbook/basic-types.html



### Funktionen:

- Funktion ninerhalb einer Konstante:

```typescript
const sum = (a: number, b:number): number => {
        return a +b 
    } 
```



kann aber auch so geschrieben werden, wenn innerhalb einer anderen funktion:

```typescript
const sum = (a:number, b:number): number => a + b
```

```typescript
 const addTodo =(text: string)=>{
    const newTodos: ITodo[] = [... todos, {text: text, completed: false}]
    setTodos(newTodos);
  }
```

### Generische Function:

- werden wird mit <> erzeugt

  - Lassen mehrere typen zu - können uns sichersein, das Typen alle identisch sind

  - ```typescript
    function myGenericFunction<T>(args: T):T[] {
        var arr: T[] = [args];
        return arr;
    }
    
    var stringArray = myGenericFunction<string>("Manu")
    var numberArray = myGenericFunction(1223);
    ```



### interfaces:

- soregn dafür, das Objekt eine gewisse Stucktur hat

  - ```typescript
    
    interface Human{
        name:string;
        age: number
    }
    
    function printHuman(human:Human): void {
        console.log("Name: " + human.name);
        console.log("age: " + human.age);
    }
    
    //Object erstellen
    var myHuman = {
        name: "Max",
        age: 20
    }
    
    printHuman(myHuman);
    ```



### Enums:

- Feste Konstante Werte, die wir auf etwas setzen können

- Können so schöneeren sprechenderen Code erzeugen

  - ```typescript
    enum Directions {
        Up,
        Down,
        Left,
        RIght
    }
    
    var dir = Directions.Up
    
    if (dir == Directions.Up) {
      console.log("Up Up and away");
    } else {
      console.log("You musst stay");
    }
    ```

### Union Types

- Type1 | Type2 

- Können nur solche Attribute verwenden, die bei allen Typen von diesem UnionType identisch sind

- Kann als Typ 2 unterscheidliche Interfaces angegeben werden

- Können aber nu die Typen benutz werden, die in beiden Interfaces vorhanden sind

  - ```
    interface Horse{
        color: string;
        age: number;
    }
    
    function printAge(age: Human): void {
        console.log("Age= " + age.age);
    }
    
    // müssten das ganze auch noch für Horse machen, wärem da nicht die Union types
    
    function printAge2(age: Human| Horse): void {
      console.log("Age= " + age.age);
    }
    //können aber nur das verwenden, was bei beiden Interfaces gleich ist
    ```



### Decoratiors:

 - Selbe Funktionen, die wir an Methoden/Klassen/Attribute andere Funktionen/usw. anhängen können. und dann ausgeführt werden, wenn wir was mit diesen Methoden machen(ausführen oder Instanz erzeugen) 

 - Gesetzt wird der Dacorator mit @NameDesDecorators

    - ```typescript
      class Person {
        public name: string;
        public surname: string;
      
        constructor(name: string, surname: string) {
            console.log(" Created new Person: " + name +" "+ surname ); 
            // wenn wir das in anderen Klassen auch verwenden wollen, müssten wir Person immer anpassen, an das, was erzeugt wird
            //wollen das automatisch gelogged wird, wenn eine neue Persion oder was auch immer erzeug wird -> dafür decorators
            this.name = name;
            this.surname = surname;
        }
      
      }
      
      var p = new Person("Max", "Mustername");
      ```

    - ```typescript
      //Decorator:
      function logClass(target: any) {
        //neuer Constructor, der Mitlogged, das neue person entstanden ist
        var constr: any = function (...args) {
          console.log("Creating Object of Class: " + target.name); // bekommen namen der Klasse in der Objekt erzeugt wird
      
          var c: any = function () {
            return target.apply(this, args); // COnstructor wird aufgerufen über this mit den args die wir gesetzte haben
          };
          //prototyp soll gelich sein
          c.prototype = target.prototype
          return new c();
        };
        //auch  noch prototyp setzte
        constr.prototype = target.prototype;
        return constr;
      }
      
      ```

    - ```typescript
      @logClass
      ```

    - ```
      
      ```

   	- 

### Usestate:



- ```typescript
  const [todos, setTodos] = useState([])
  ```

  - useState mit Array

- 

- ```typescript
  const [value, setValue] = useState<Typ>("")
  ```

  - value ist ein String
  - setValue eine Funktion
  - was immer useState("HIER") drinnne stteht ist unser default Vaslue
  - wenn wir den inhalt ändern wollen, müssen wir die setValue Funktion aufrufen

- Anwendung:

  - ```html
    <input type="text" value={value} onChange={e => setValue(e.target.value)} required />
    ```

  - ```typescript
     const handleSubmit = (e:FromElem): void => {
        e.preventDefault() // haltet sie Side davon ab, sich zu refreshen
        setValue("")
      }
    ```

  - damit der Type für e nicht immer so lange ausgeschrieben werden muss, macht man eine typ-Variable dafür : 

  - ```typescript
    type FromElem = React.FormEvent<HTMLFormElement>; 
    ```

- 1

- 2

  ### Type 

  - referenziert auf einen anderen typen

    -  ```typescript
      type FromElem = React.FormEvent<HTMLFormElement>; 
       ```

      

### Interfsace:

- ```typescript
  Interface ITodo {
  text: String
  complete: boolean
  }
  ```

  - Um einen neuen, eigernen typen zu kreieren

  - Können erweitert werden:

    - ```typescript
      interface ITodo2 extends ITodo {
        tags: string[]
      }
      ```

      

    - 

- 

### Diesdas:

- debugger im code setzt einen breakpoint
- Rfc shortcut
- clg shortcut
- **|** steht für "oder"

- **!** Hinter einem Ausdruck gint an, das es nie null wird

  - const *input1* = *document**.**getElementById*("num1")! *as* *HTMLInputElement*;

-  tsc ftypeScriptFileName.ts wandelt ts in nei js file um

- <> </> = steht für anfang und endtag eines Fragments

- Formatiert in vd code:

  - shift option f

  ### Compilieren einer ts file:

  npm init generiert **package.json file**

-  npm install --save -dev lite-server generiert **package-lock.json**

- ```html
  <button type="button" onClick={() => completeTodo(index)}/> {todo.complete? "Incomplete": "Complete"}
  ```

  - nach dem closingTag wird inKlammen ein Text. Angegeben, der 2 verschiedene. Werte haben kann, jenachdem ob Todo fertof oder nicht fertig ist

-  splice: löscht ein array

  - ```typescript
    arr = [0,1,2,3,4]
    arr.splice(1,2)
    output: [0,3,4]
    ```

- 

- 

  

- 

### Arrow-Functions:

- Der **Ausdruck einer Pfeilfunktion** hat eine kürzere Syntax als ein [Funktionsausdruck](https://developer.mozilla.org/de/docs/Web/JavaScript/Reference/Operators/function) und hat kein eigenes `this`, [arguments](https://developer.mozilla.org/de/docs/Web/JavaScript/Reference/Functions/arguments), [super](https://developer.mozilla.org/de/docs/Web/JavaScript/Reference/Operators/super), oder [new.target](https://developer.mozilla.org/de/docs/Web/JavaScript/Reference/Operators/new.target). Solche Funktionsausdrücke sind am besten für Funktionen, die nicht als Methode genutzt werden, geeignet und können nicht als Konstruktoren verwendet werden. Verwendet wenn wir den state innerhalb der Funktion verändern wollen und this. Verwenden.

```javascript
 handleClick = (e) => {
          console.log(this.state);
        }
```







