## Espresso

#### add dependencies

- testInstrumentRunner 'android.support.test.runner.AndroidJumitRunner'

#### Start Espresso:

Run-Record Espresso Test 

#### class für Tests erstellen

- Neu klasse in (AndroidTest) hinzufügen

- ```Kotlin
  @RunWith (AndroidJUnit4 :: class) 
  Klasse LoginTest { 
      @JvmField 
     @Rule 
     var mActivityRule: ActivityTestRule <MainActivity> = ActivityTestRule (. MainActivity :: Klasse java ) 
  
      @Test Spaß test_Login_HasPasswordOfMoreThan6Letters () 
      { 
          OnView (. WithId (R.id username )) 
                  .perform (typeText ("ngengesenior")) 
  
          onView (withId (R.id. password )) 
                  .perform (typeText ("password")) 
  
          onView (withId (R.id. buttonLogin )) 
                  .check (matches (isDisplayed () )) 
                  .perform (click ()) 
  
          onView (withId (R.id. appIcon)) 
                  .check (matches (isDisplayed ())) 
  
      } 
  
  
  } //am Afang der class um zu definieren, dass Tests geschriben werden
  ```



## Erklärung des Codes

1. Wir erstellen unsere LoginTest-Klasse und kommentieren sie mit der @ RunWith (AndroiJUnit4) -Klasse.
2. Erstellen Sie die Variable mActivityTestRule für MainActivity (Aktivität, für die der Test ausgeführt werden soll).
3. Erstellen Sie unsere Testfunktion test_Login_HasPasswordOfMoreThan6Letters und kommentieren Sie sie mit @Test.
4. Suchen Sie EditText mit der ID, dem Benutzernamen und führen Sie eine Aktion durch, indem Sie den Text "ngengesenior" eingeben.
5. Suchen Sie EditText mit ID, Kennwort und führen Sie eine Aktion durch, indem Sie den Text "Kennwort" eingeben.
6. Überprüfen Sie, ob die Schaltfläche mit der ID buttonLogin angezeigt wird, und klicken Sie auf die Schaltfläche
7. Überprüfen Sie, ob die ImageView mit ID, AppIcon angezeigt wird.

In diesem Fall ist der Test bestanden, da unser Benutzername nicht leer ist und unser Passwort größer als 6 ist.

<img src="https://testyour.app/static/ac9ab2063496fa78f5029d98e32854e0/8eb14/uiautomator_cheat_sheet.jpg" alt="Bildergebnis für android espresso cheat sheet" style="zoom:150%;" />



```Kotlin
launchActivity(StartupActivity::class.java) // um app zu starten
```

- Um Breakpoint zu sehen muss die app im Debug gestartet werden
- im build.grade lasst sich die adresse für den localhost umstellen

### build.gradle

```kotlin
implementation"org.jetbrains.kotlin:kotlin-stdlib-jdk7:1.2.7"
implementation 'androidx.appcompat:appcompat:1.0.0'
implementation 'androidx.constraintlayout:constraintlayout:2.0.0-alpha2'
testImplementation 'junit:junit:4.12'
androidTestImplementation 'androidx.test:runner:1.1.0-beta02'
androidTestImplementation 'androidx.test.espresso:espresso-core:3.1.0-beta02'
androidTestImplementation 'androidx.test:rules:1.1.0-beta02'
androidTestImplementation 'androidx.test.ext:junit:1.0.0-beta02'
```



### Ablauf

1. Suchen Sie EditText mit der ID name_field und geben Sie das Wort "Steve" in das Namensfeld ein
   1. **onView (withId (R.id.name_field)). Perform (typeText ("Steve"));** 
2. Suchen Sie die Schaltfläche mit der ID greet_button und klicken Sie auf
   1.  **onView (withId (R.id.greet_button)). perform (click ());** 
3. Ü**berprüfen Sie, ob die Ansicht mit dem Text „Hallo Steve“ angezeigt wird**
   1.  **onView (withText ("Hallo Steve!")). check (matches (isDisplayed ());**

Die Tests befinden sich im androidTest-Paket 

### Auf App-Code zugreifen

```kotlin
InstrumentationRegistry.getInstrumentation().targetContext.
```

### Überprüfen von Elementsn

- **ViewMatchers** enthält Methoden, mit denen Espresso die Ansicht auf Ihrem Bildschirm findet, mit der es interagieren muss.
- ***ViewActions*** enthält Methoden, die Espresso mitteilen, wie die Benutzeroberfläche automatisiert werden soll. Es enthält beispielsweise Methoden `click()`, mit denen Sie Espresso anweisen können, auf eine Schaltfläche zu klicken.
- ***ViewAssertions*** enthält Methoden, mit denen überprüft wird, ob eine Ansicht bestimmten Bedingungen entspricht.

### *Übereinstimmende Ansichten mithilfe von Text*

Sie können Ansichten nach vielen anderen Kriterien als ihrer ID zuordnen, z. B. nach Text. Probieren Sie dies aus, während Sie auf die Schaltfläche *OK* prüfen . Fügen Sie Ihrer Testklasse den folgenden Test hinzu:

```kotlin
@Test
fun onLaunchOkayButtonIsDisplayed() {
  ActivityScenario.launch(MainActivity::class.java)

  onView(withText(R.string.okay))
      .check(matches(isDisplayed()))
}
```



Der Hauptunterschied besteht darin, dass Sie `withText()`statt verwenden `withId()`. Sie können dieser Funktion beide Referenzen auf String-Ressourcen wie oben oder String-Literale übergeben.

### Aktion ausführen

```kotlin
@Test
fun whenOkayButtonIsPressedAndAmountIsEmptyTipIsEmpty() {
  ActivityScenario.launch(MainActivity::class.java)

  // 1
  onView(withId(R.id.buttonOkay))
      .perform(click())

  // 2
  onView(allOf(withId(R.id.textTip), withText("")))
      .check(matches(isDisplayed()))
}
```

-  `.perform()`, um verschiedene Aktionen in einer Ansicht auszuführen .
- `allOf()` um Espresso mit zu teilen, dass beide Bedingungen für die Anzeige erfüllt sein müssen -**(org.hamcrest.Matchers.allOf)**



### *Text eingeben*

```kotlin
@Test 
Spaß,  wennOkayButtonIsPressedAndAmountIsFilledTipIsSet () {
  ActivityScenario.launch (MainActivity :: class . Java )

  // 1
  onView (withId (R.id.inputAmount))
      .perform (typeText ( "11" ))

  onView (withId (R.id.buttonOkay))
      .perform (click ())

  // 2
 onView(withId(R.id.textTip))
      .check(matches(withText("1.98")))
}
```

-  `.perform(typeText("11"))`um diesen Text in das Feld einzugeben.
- Sie überprüfen, ob die Ansicht mit der ID `textTip`den richtigen Text enthält, `withText()`indem Sie `allOf()`und kombinieren `isDisplayed()`. Dies ist eine alternative Möglichkeit, diese Prüfung durchzuführen.

### Matches

onVie(withId(R.id.namederactivity)).check(matches(ViewMatchers.withText(R.string.nameDerVariableWoTextGespeichert)))

### Wait

- idlingRessources

### performances

- `typeText()` to imitate typing text into an `EditText`.
- `clearText()` to simulate clearing text in an `EditText`.
- `doubleClick()` to simulate double-clicking a `View`.
- `longClick()` to imitate long-clicking a `View`.
- `scrollTo()` to simulate scrolling a `ScrollView` to a particular `View` that is visible. 
- `swipeLeft()` to simulate swiping right to left across the vertical center of a `View`. (onView(withId(R.id.onboarding_slideshow_viewpager)).perform(ViewActions.swipeLeft()))

### 3 wichtige Gruppen

1. ViewMatchers - Etwas in der View finden
2. ViewActions - Etwas tun
3. ViewAssertions - Etwas prüfen

###  View Matchers 

 /Users/mamed/Library/Android/sdk/tools/bin/uiautomatorviewer‚

- with id:
  - onView(withid(R.id.NAMEDERRESSOURCE)) -> wenn verweif auf das Element bekannt
- with Text:
  - onView(withText("TEXTDERAUFDERVIEWANGEBIELDETWIRD"))
- with description:
  - onView(withCintentDescription("DASWASALSCONTENDTDIS.ANGEGEBNIST"))
- with Hint Text:
  - onView(withHint("??????")) -> Returns a matcher that matches a descendant of `TextView` that is displaying the hint associated with the given resource id.
- With spinner rext
  - inView(withSpinnerText("????"))
- Return TextView with links
  - onView(hasLInks())

### Custom Matchers

- Selber einem  Matcher definieren.
- dafür neue class in AndroidTest anlegen

```Kotlin
override fun matchesSafely(b: TextView): Boolean {
    actualItemId = b.imeActionId
    return actualItemId == dateId
}
```

- `describeTo`ermöglicht es uns, dem benutzerdefinierten Matcher eine eigene Beschreibung hinzuzufügen. Beispielsweise

  description?.appendText("RecyclerView with item count: $count")

- **`matchSafely` Hier implementieren wir die Vergleichslogik für die Stückzahl.**

  - ```Kotlin
    return item?.adapter?.itemCount == count
    ```

The completed `CustomMatchers` should look like this:

```Kotlin
class CustomMatchers {
  companion object {
    fun withItemCount(count: Int): Matcher<View> {
      return object : BoundedMatcher<View, RecyclerView>(RecyclerView::class.java) {        override fun describeTo(description: Description?) {
          description?.appendText("RecyclerView with item count: $count")
        }

        override fun matchesSafely(item: RecyclerView?): Boolean {
          return item?.adapter?.itemCount == count
        }
      }
    }
  }
}
```

