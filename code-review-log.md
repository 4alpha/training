###### Tue Dec 27, 2016
```javascript
function showPanel() {
  if (user.role == 'Admin' || user.role == 'Super Admin'){
    return true;
  }
  if (user.role == 'Sales Manager' || user.role == 'Borrower Specialist' || user.role == 'Investor Specialist'){
    return true;
  }

  if (user.role == 'Borrower' || user.role == 'Investor'){
    return false;
  }
}
```

```javascript
function showPanel() {
  if (isAdmin(user) || isManager(user)){
    return true;
  }
  return false;
}
```
