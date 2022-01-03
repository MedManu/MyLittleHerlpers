# .Pandas

Doku: https://pandas.pydata.org/pandas-docs/stable/



## Series:

- array mit Index
- mit dem index können Date naus de marray abgerufebn werden

```python
import pandas as pd
import numpy as np

labels = ["a","b","c"]
my_List =[10,20,30]

arr = np.array([10,20,30])
dic = {'a':10, 'b':20, 'c': 30}

pd,.Series(data=my_List,index=labels)

```



## DataFrame:

```python
colums = ['W','X','Y','Z']
index = ['A','B','C','D','E']
data = randint(-100,100,(5,4)) von - bis + 100 5 Zeilen und 4 Spalten

df = pd.DataFrame(data,index,columns)

#eine Spalte aufrufen
df['W']
#zwei Spalten aufrufen
df[['W','Z']]
#Zeilen ausgeben
df.loc[['A','B']]
#Erste Zeile des Index ausgeben
df.iloc[0]
#Index 0 bis exclusive 2
df.iloc[0:2]
#neue Spalte eunfügen
df['nmeDerSpalte'] = df['Werte']
df['neu'] = df['W'] + df['Y']
#Spalte entfernen
df.drop('nameDerSpalte', axis= 1=Spalte,0=Zeile)
#Aänderungen müssen immer dem Dataframe zugewiesen werden damit sie übernommen werden
# mit inplace = ture wird es automatisch neu generiert!!! Aber besser nicht so machen!
df= df.drop('neu', axis = 1)
#Zeile entfernen
df.drop('C',axis=0)
#slicing - auschneiden
df.loc[['Zeile1','Zeile2'], ['Spalte']]
df.loc[['A','D'], ['W']]
#Bedingte auswahl
df>0
df['Spalte'] > 0 #ausgabe in True oder Fasle
df[df['Splate']>0] #ausgabe der Zahlen
#Filtern in der neuen Ausgabe
df[df['X']>0][['X','Y']]
#Bedingung
df[(df['W'] > 0) & (df['Y'] > 1)]
#Index löschen
df.reset_index() # Index wird dann als Splate eingefügt
#Neuen Index Setzte
##1 Nen Index erstellen
newIndex = 'e','a','t','j','h'
##2 Index zu neuer Spalte machen
df['SpaltenName'] = newIndex
##Spalte als Index setzten
df.set_index/('SpaltenName')
#Infos bekommen
df.describe()
df.info()
df.types()
```



## Fehlende Daten

```python
#Löschen
## Es wird aber die gesammte Zeile/Spalte entfernt
df.dropna(axis=1 oder 0)
##thresh= wieviele nicht 0 Werte wir haben möchten
df.dropna(thresh=2)
#Füllen
df.fillna(value='WertDerStehenSoll')
#Wert aus Spalte 0 setzen
df['A'].fillna(0)
#Wert einer Spalte mit Durchschnitt füllen
df['A'].fillna(df['A'].mean())
#Wert aller Spalten mit ihrem Durchschnitt auffüllen
df.fillna(df.mean())
```

## Group by

```python
#Datei laden
df = pd.reas_csv('Pfad')
#Groupby muss immer mit einer aggregatFunktion übergeben werden
df.groupby('SpaltenName').mean()/sum()/min()/max()/count()
#Absteigend nach Index sortieren absteigend = Flasem aufsteigend = True
df.groupby('').mean().sort_index(ascending=False)
#Nach meheren Werten gruppieren
df.groupby(['Wert1', 'Wert2']).mean()
#Beschreiben transpose = ändert die Darastellung
df.groupby('Year').describe().transpose()
```

## Operatoren

```python
#Uniquwqe Werte anzeigen
df['Spalte'].unique()
#Anzahl der uniquen Werte
df['Spalte'].nunique()
#Anzahl der werte in einer Spalte
df['Spalte'].value_counts()
#duplicate entfernen
df['Spalte'].drop_duplicates()
```

