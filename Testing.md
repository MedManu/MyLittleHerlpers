# 2e2 with puppeteer



## Test-Funktionen

### descripe

The `describe` function acts as a container that’s used to create a block that groups related tests into one test suite. This can be helpful if you want your tests to be organized into groups. The `test` function is declared by Jest with the name of the test suite.

```javascript
describe('H1 Text', () => {
  test('h1 loads correctly', async () => {
    let browser = await puppeteer.launch({
      headless: false
    });
    let page = await browser.newPage();
    await page.waitForSelector(".App-title");
```



### emulate

The `.emulate()` function gives you the ability to emulate certain device metrics and User-agent. In the code block above, we set it to have a viewport of `500x2400`.

```json
  page.emulate({
      viewport:{
        width: 500,
        height: 2400
      },
      userAgent: ""
    })
```



### waitForSelector

The `.waitForSelector()` function tells Puppeteer to hold on until the particular selector has been loaded on the DOM. Once it’s loaded, the `innerText` of that selector is stored in a variable called `html`.



## Gehn zu einer Seite

```javascript
await page.goto("http://http://localhost:3000/");

await page.waitForSelector(".App-title");
```

