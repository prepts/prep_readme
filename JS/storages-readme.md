

# JS Storage

### Explanation

- JavaScript provides three mechanisms for storing data. Each one has advantages and disadvantages.

### Different types of Storage

- Local storage
- Session storage
- Cookies

## Local storage

Local storage is the most recent mechanism. It allows for larger amounts of data to be stored, but the data is not deleted when the browser is closed. Local storage is useful for storing data that the user will need to access later, such as offline data.

## Session storage

Session storage is similar to Local storage, but the data is only stored for the current session. This means that the data will be deleted when the user closes the browser. Session storage is useful for storing data that is sensitive, such as login credentials.

#### Local and Session storage has 4 methods:

- setItem()
This method takes two parameters one is key and another one is value. It is used to store the value in a particular location with the name of the key.
```
localStorage.setItem(key, value)
sessionStorage.setItem(key, value)
```
- getItem()
This method takes one parameter that is key which is used to get the value stored with a particular key name.
```
localStorage.getItem(key)
sessionStorage.getItem(key)
```
- removeItem()
This is method is used to remove the value stored in the memory in reference to key.
```
localStorage.removeItem(key)
sessionStorage.removeItem(key)
```
- clear()
This method is used to clear all the values stored in localstorage.
```
localStorage.clear()
sessionStorage.clear()
```

## Cookies
Cookies are primarily used for server-side access and can be read by the server when a user makes a request.They are automatically included in every HTTP request made to the server, which can increase the amount of data transferred over the network.

## Difference Between Local Storage, Session Storage, And Cookies

![Difference between the storages](https://i.ibb.co/PFT7h6b/js-storage.png)