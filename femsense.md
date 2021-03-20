## Crossplatform auf Handy:

- In capacitor.config.json in main root:

```
"server": {"url": " http://192.168.0.24:3000"}
```

- Path for Android: `android/app/src/main/assets/capacitor.config.json`
- Path for iOS: `ios/App/App/capacitor.config.json`
- npm run build sync  
- npx cap copy ios  
- npx cap open ios  



- chrome://inspect/#devices

```
const [rangeValue, setRangeValue] = useEffect<{
  lower: number;
  upper: number;
}>({ lower: minLength ?? 0, upper: maxLength ?? 0 });
```



```
const [rangeValue, setRangeValue] = useState<{
  lower: number;
  upper: number;
}>({ lower: minLength ?? 0, upper: maxLength ?? 0 });

useEffect(() => {
}, [rangeValue]);
```

## Cropssplatform

### Classen:

```typescript
class NameDerKlasse extends React.Component<AppState> {}
```

### Export der klassse

```
export const MyVarableName = connect<AppState, {}, {}, AppState>((state: AppState) => {
return state
}(NameDerKlasse)
)
```

### backend Account bearbeiten

```
curl\
  -X POST -d '{"email":"test1@steadysense.at","password":"abc123abcxyz"}'\
 -H "Accept: application/json" \
 -H "Content-Type: application/json" \
https://app.staging.femsense.com/api/v1/auth/login/
```

## Eigener Account

- {"key":"68f01bda117c78c9b1b10389f4f600bfeac531c5"}%    
  -  curl\
      -X POST -d '{"email":"tester1622@femsense.com","password":"testermtesterm"}'\
     -H "Accept: application/json" \
     -H "Content-Type: application/json" \
    https://app.staging.femsense.com/api/v1/auth/login/

- Tokken der da rauskommt dann in femsense-capasitor-browser.ts eingeben
- dann im femsense backend suchen

cmd K -> commit

Cmd opt K