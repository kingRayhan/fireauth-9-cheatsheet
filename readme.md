#### Initialization

```js
import { initializeApp } from "firebase/app";
import { getFirestore } from "firebase/firestore";

const config = {
  apiKey: "xxxx",
  authDomain: "xxxx",
  projectId: "xxxx",
  storageBucket: "xxxx",
  messagingSenderId: "xxxx",
  appId: "xxxx",
};


export const app = initializeApp(config);
export const auth = getAuth(app);
```

**Create User**

```js
import { createUserWithEmailAndPassword } from 'firebase/auth';

await createUserWithEmailAndPassword(
  auth,
  email,
  password,
)
```


**Signin using email and password**
```js
import { signInWithEmailAndPassword } from 'firebase/auth';

await signInWithEmailAndPassword(
  auth,
  email,
  password,
)
```


**Authenticated user observer**
```js
import { onAuthStateChanged } from "firebase/auth";

onAuthStateChanged(auth, (user) => {
  if (user) {
    // User is signed in, see docs for a list of available properties
    // https://firebase.google.com/docs/reference/js/firebase.User
    const uid = user.uid;
    // ...
  } else {
    // User is signed out
    // ...
  }
});
```
