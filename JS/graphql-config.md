

# GrpahQL config

```javascipt
import { ApolloClient, createHttpLink, InMemoryCache } from "@apollo/client";
import { setContext } from "@apollo/client/link/context";
import { onError } from "@apollo/client/link/error";

const link = setContext((_, { headers }) => {
  // get the authentication token from local storage if it exists
  const User = JSON.parse(localStorage.getItem("User"));
  const accessToken = User ? `Bearer ${User.token}` : "";
  // return the headers to the context so httpLink can read them
  return {
    headers: {
      ...headers,
      authorization: accessToken,
    },
  };
});

const httpLink = createHttpLink({
  uri: process.env.REACT_APP_GRAPHQL_SERVER,

  //'same-origin'   if your backend server is the same domain
  //'include'   if your backend is a different domain
  credentials: "same-origin",
});

// Log any GraphQL errors or network error that occurred
const errorLink = onError(({ graphQLErrors, networkError }) => {
  if (graphQLErrors)
    graphQLErrors.forEach(({ message, locations, path }) => {
      // if (extensions.code === "UNAUTHENTICATED") {
      //   localStorage.removeItem("User");
      //   window.location.href = process.env.REACT_APP_LOGOUT_REDIRECT_URL;
      // }
      console.log(`[GraphQL error]: Message: ${message}, Location: ${locations}, Path: ${path}`);
    });
  if (networkError) console.log(`[Network error]: ${networkError}`);
});

const authLink = link.concat(errorLink);

const cache = new InMemoryCache();

export default function createApolloClient() {
  return new ApolloClient({
    link: authLink.concat(httpLink),
    cache,
    defaultOptions: {
      watchQuery: {
        fetchPolicy: "cache-and-network",
        errorPolicy: "all",
      },
      query: {
        fetchPolicy: "network-only",
        errorPolicy: "all",
      },
      mutate: {
        errorPolicy: "all",
      },
    },
  });
}

```
