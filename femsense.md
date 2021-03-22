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
  -X POST -d '{"email":"donot017@gmx.net","password":"donot019!"}'\
 -H "Accept: application/json" \
 -H "Content-Type: application/json" \
https://app.staging.femsense.com/api/v1/auth/login/
```



- Tokken der da rauskommt dann in femsense-capasitor-browser.ts eingeben
- dann im femsense backend suchen

feature/CalendarBarDesignUpdate

```
10ca71c5e38657456c4cbe4bafb5e0e5dd1d8411
```