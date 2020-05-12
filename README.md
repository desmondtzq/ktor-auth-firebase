# ktor-auth-firebase

Provides an AuthenticationProvider that verifies firebase id token. This is based on the [implementation](https://github.com/ktorio/ktor/blob/master/ktor-features/ktor-auth-jwt/jvm/src/io/ktor/auth/jwt/JWTAuth.kt) of [ktor-auth-jwt](https://ktor.io/servers/features/authentication/jwt.html).

## Usage

Install the authentication feature and set up the firebase authentication provider.

In the validate function, `credential` is given, which contains a verified [FirebaseToken](https://firebase.google.com/docs/auth/admin/verify-id-tokens). You can then return an instance of Principal using the token.

``` kotlin
val firebaseApp: FirebaseApp = // ...

authentication {
    firebase(firebaseApp) {
        validate { credential ->
            // return Principal using credential
        }
    }
}
```

## Download

Adding a gradle dependency: 
``` groovy
implementation "com.desmondtzq.ktor:ktor-auth-firebase:1.0.1"
```

## License
```
Copyright 2020 Desmond Teo.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```
