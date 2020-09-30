# CSS-Tricks and helper

### Position:

- control K --> shortcut liste
- Shift option f --> formatieren



### Layout-Beispiele:

```css

html{
  font-size: 14px;
}

body {
  margin: 0;
  font-size: 12px;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Roboto', 'Oxygen',
    'Ubuntu', 'Cantarell', 'Fira Sans', 'Droid Sans', 'Helvetica Neue',
    sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.episode-layout {
  display: flex;
  flex-wrap: wrap;
  min-width: 100vh;
}

.episode-box {
  padding: .5rem
}

.header {
  display: flex;
  justify-content: space-betrween;
  background: white;
  border-bottom: 1px solid black;
  padding: .5rem;
  position: sticky;
  top: 0;
}

```







