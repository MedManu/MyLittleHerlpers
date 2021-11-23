# Testing-library-react:

## Component tests mit react

### Test Aufbau

```typescript
mport {assert} from 'assertthat'
const sum = (summand1: number, summan2: number) => summand1 + summan2;

console.log(sum(2,3))

describe('WelcheKomponentewirdgetestet', (): void => {
    it('wasmachtDerTest', async (): Promise<void> => {
        //testaufbau:
        //1; arrange -> test aufbauen
        const summand1 = 2;
        const summand2 = 3;

        //2: act -> test ausführen
        const result = sum(summand1, summand2)

        //3: assert -> entspricht das resultat unseren erwartungen
        assert.that(result).is.equalTo(5)

    })
})
```



