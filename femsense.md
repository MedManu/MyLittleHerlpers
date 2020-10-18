```
server: {"url": " http://192.168.0.24:3000"}
```







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