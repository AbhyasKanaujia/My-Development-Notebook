# JSON Web Tokens

JWT("jot") is a standard for _safely_ passing _claims_ in space-constrained environments.

A JWT looks like this:

{% code overflow="wrap" %}
```

eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiYWRtaW4iOnRydWV9.TJVA95OrM7E2cBab30RMHrHDcEfxjoYZgeFONFh7HgQ
```
{% endcode %}

When Decoded, it reads:&#x20;

```json
{
  "alg": "HS256",
  "typ": "JWT"
}

{
  "sub": "1234567890",
  "name": "John Doe",
  "admin": true
}
```

Claims are _definitions_ or _assertions_ made about a certain party or object.

The given example is of an identity claim that uses _sub._

JWTs can be signed and/or encrypted using JSON Web Signatures and JSON Web Encryption.&#x20;

## Applications of JWT

* Authentication&#x20;
* Authorization&#x20;
* Federated identity&#x20;
* Client-side sessions (“stateless” sessions)&#x20;
* Client-side secrets

\#
