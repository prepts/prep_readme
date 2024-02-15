

# Axios

### Explanation

- Axios is a popular JavaScript library used for making HTTP requests which supports making requests in both browser and node.js environment
- Axios is commonly used in web applications for communicating with APIs and fetching data asynchronously

### Features

- Error Handling
- Simple API requests
- Promise-based API
- Client-Side Security
- Automatic JSON Data Parsing
- Interceptors

## Simple request

we can make API requests using axios pre-defined methods such as get, post, patch, put, delete

#### Simple GET request [example 1]

```
axios.get('https://jsonplaceholder.typicode.com/posts/1')
  .then(response => {
    console.log(response.data);
  })
  .catch(error => {
    console.error(error);
  });

```
#### Simple POST request [example 2]

```
axios.post('https://jsonplaceholder.typicode.com/posts', postData)
  .then(response => {
    console.log(response.data);
  })
  .catch(error => {
    console.error(error);
  });

```

## Instance

we can create an instance using axios where we can configure common requirments, so that we can use the instance globally through out the app

- baseUrl
- headers
- method
- params

```
import axios from "axios";

const axiosInstance = axios.create({
  baseUrl: "https://jsonplaceholder.typicode.com",
  headers: {
    "Content-Type": "application/json",
  },
});

```

use the created axios instance for making API request

#### GET request [example 1]

``` 
axiosInstance.get('/posts/1')
  .then(response => {
    console.log(response.data);
  })
  .catch(error => {
    console.error(error);
  });

```

#### POST request [example 2]

``` 
customAxios.post('/posts', postData)
  .then(response => {
    console.log(response.data);
  })
  .catch(error => {
    console.error(error);
  });

```

## Interceptors

### Features

- Request Interceptors
- Response Interceptors
- Error Handling
- Retry Mechanism
- Conditional Interceptors
- Global Configuration

### Realtime Usecases

- Append auth token for priavte API request
- Destructing the required data from the response
- Showing toaster based on the results
- Log results in dev environment globally
- Implement loader functionality globally for all the API calls

#### Request Interceptor [example 1]

```
axiosInstance.interceptors.request.use(
  (config) => {
    if (config?.params?.isAuthRequired) {
      config.headers.authorization = `Bearer ${getItem("authtoken")}`;
    }

    config.params = omit(config.params, "isAuthRequired");

    return config;
  },
  (err) => {
    return Promise.reject(err);
  }
);

```

#### Response Interceptor [example 2]

```
axiosInstance.interceptors.response.use(
  (response) => {
    // parse response data if required

    return response.data;
  },
  (err) => {
    if (err.response.status === 401) {
      // refresh token logic goes here
    }

    return Promise.reject(err);
  }
);

```
