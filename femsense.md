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

