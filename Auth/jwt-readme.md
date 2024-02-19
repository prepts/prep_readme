

# JWT (JsonWebToken)

### Explanation

- Jwt is a popular mechanism used for managing auth tokens
- Jwt's are digitally signed, and secured using algorithms for confidentiality
- Jwt can be splitted to three parts using a dot, header, payload and signature
- Jwt is used as an identifier when making requests between client and server

### Features

- Safe and secure
- Self-contained (has all info with in itself)
- Stateless (no need to maintain any session in server)
- Cross-domain compatibility (can be used by multiple servers)

### Methods provided by Jwt

- sign
- verfiy
- decode

#### sign method

- sign method will return a token where the provided info will be stored in a encrypted form
- we can provide a custom expiration time using expiresIn, ex: 300 (milliseconds) where the token will be expired after 5 minutes
- Jwt provides many algorithms, we can use accordind to our choice

```
jwt.sign({ your_info }, your_secret_key, {
  expiresIn: your_expiration_time, 
});

```
#### decode method

- decode method is provided by Jwt to decode the info stored in token
- token is seperated by 3 dots, header, payload and signature

```
const token = 'your_token';
const decoded = jwt.decode(token)

console.log(decoded)

```

![decode-example-image](https://i.ibb.co/HVWZLY6/Screenshot-from-2024-02-19-13-06-10.png)

#### verify method

- verify method is provided by Jwt to verifying the token
- secret key is required for using verify method
- verify method can be used as a middleware to check is the token valid before accesing private API


```
const token = 'your_token';
const secret_key = 'your_secret_key';

jwt.verify(token, secretKey, (err, decoded) => {
  if (err) {
    if (err.name === 'TokenExpiredError') {
      console.log('Token is expired');
    }

    if (err.name === 'JsonWebTokenError') {
      console.log('Token is invalid');
    }
  } else {
    console.log('Token is valid');
  }
})


```
