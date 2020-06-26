# Styled Components


### Pass props to a styled component without typescript compiler complaining
```javascript
const Wrapper = styled.div<{ propName: Type }>`
```
Now you can use like this
```javascript
color: ${prop => prop.propName}
```