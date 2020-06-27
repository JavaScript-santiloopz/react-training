# Rendering

### Conditional rendering with the && operator
Light syntax for conditional rendering
```javascript
{unreadMessages.length > 0 &&
    <h2>You have {unreadMessages.length} unread messages.</h2>
}
```
For if else, use the ternary
```javascript
{isLoggedIn ?
    <LogoutButton onClick={this.handleLogoutClick} /> :
    <LoginButton onClick={this.handleLoginClick} />
}
```
When you don't want to render a component depending on the props received, 
use the `return null` in the render method.
