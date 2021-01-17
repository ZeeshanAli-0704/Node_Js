# JWT Interview Questions
 
 #### JSON Web Token (JWT)
 [Introduction](https://jwt.io/introduction/)
 
## Brief of JSON WEB TOKEN
A JWT technically is a mechanism to verify the owner of some JSON data. It’s an encoded string, which is URL safe, that can contain an unlimited amount of data (unlike a cookie), and it’s cryptographically signed.

When a server receives a JWT, it can guarantee the data it contains can be trusted because it’s signed by the source. No middleman can modify a JWT once it’s sent.

It’s important to note that a JWT guarantees data ownership but not encryption; the JSON data you store into a JWT can be seen by anyone that intercepts the token, as it’s just serialized, not encrypted.

For this reason, it’s highly recommended to use HTTPS with JWTs (and HTTPS in general, by the way).

> JWT is an abbreviation for JSON Web Token, which is a compact URL-safe means of representing claims to be transferred between two parties. The claims in a JWT are encoded as a JSON object that is digitally signed using JSON Web Signature (JWS). ~ IETF

JWT tokens consists of three parts separated by dots.
```
header.payload.signature
```
OR
```
x.y.z
```
### Header

The header  _typically_  consists of two parts: the type of the token, which is JWT, and the signing algorithm being used, such as HMAC SHA256 or RSA.

For example:

```
{
  "alg": "HS256",
  "typ": "JWT"
}

```

Then, this JSON is  **Base64Url**  encoded to form the first part of the JWT.

### Payload

The second part of the token is the payload, which contains the claims. Claims are statements about an entity (typically, the user) and additional data. There are three types of claims:  _registered_,  _public_, and  _private_  claims.

-   [**Registered claims**](https://tools.ietf.org/html/rfc7519#section-4.1): These are a set of predefined claims which are not mandatory but recommended, to provide a set of useful, interoperable claims. Some of them are:  **iss**  (issuer),  **exp**  (expiration time),  **sub**  (subject),  **aud**  (audience), and  [others](https://tools.ietf.org/html/rfc7519#section-4.1).
    
    > Notice that the claim names are only three characters long as JWT is meant to be compact.
    
-   [**Public claims**](https://tools.ietf.org/html/rfc7519#section-4.2): These can be defined at will by those using JWTs. But to avoid collisions they should be defined in the  [IANA JSON Web Token Registry](https://www.iana.org/assignments/jwt/jwt.xhtml)  or be defined as a URI that contains a collision resistant namespace.
    
-   [**Private claims**](https://tools.ietf.org/html/rfc7519#section-4.3): These are the custom claims created to share information between parties that agree on using them and are neither  _registered_  or  _public_  claims.
    

An example payload could be:

```
{
  "sub": "1234567890",
  "name": "John Doe",
  "admin": true
}

```

The payload is then  **Base64Url**  encoded to form the second part of the JSON Web Token.

> Do note that for signed tokens this information, though protected against tampering, is readable by anyone. Do not put secret information in the payload or header elements of a JWT unless it is encrypted.

### Signature

To create the signature part you have to take the encoded header, the encoded payload, a secret, the algorithm specified in the header, and sign that.

For example if you want to use the HMAC SHA256 algorithm, the signature will be created in the following way:

```
HMACSHA256(
  base64UrlEncode(header) + "." +
  base64UrlEncode(payload),
  secret)

```

The signature is used to verify the message wasn't changed along the way, and, in the case of tokens signed with a private key, it can also verify that the sender of the JWT is who it says it is.

### Putting all together

The output is three Base64-URL strings separated by dots that can be easily passed in HTML and HTTP environments, while being more compact when compared to XML-based standards such as SAML.

The following shows a JWT that has the previous header and payload encoded, and it is signed with a secret.  

![Encoded JWT](https://cdn.auth0.com/content/jwt/encoded-jwt3.png)

## When should you use JSON Web Tokens?

Here are some scenarios where JSON Web Tokens are useful:

-   **Authorization**: This is the most common scenario for using JWT. Once the user is logged in, each subsequent request will include the JWT, allowing the user to access routes, services, and resources that are permitted with that token. Single Sign On is a feature that widely uses JWT nowadays, because of its small overhead and its ability to be easily used across different domains.
    
-   **Information Exchange**: JSON Web Tokens are a good way of securely transmitting information between parties. Because JWTs can be signed—for example, using public/private key pairs—you can be sure the senders are who they say they are. Additionally, as the signature is calculated using the header and the payload, you can also verify that the content hasn't been tampered with.

## Store JWTs securely

A JWT needs to be stored in a safe place inside the user’s browser.

If you store it inside localStorage, it’s accessible by any script inside your page (which is as bad as it sounds, as an XSS attack can let an external attacker get access to the token).

**Don’t store it in local storage (or session storage)**. If any of the third-party scripts you include in your page gets compromised, it can access all your users’ tokens.

The JWT needs to be stored inside an **httpOnly cookie**, a special kind of cookie that’s only sent in HTTP requests to the server, and it’s never accessible (both for reading or writing) from JavaScript running in the browser.

## JSON WEB TOKEN BEST PRACTICES

Before we actually get to implementing JWT, let’s cover some best practices to ensure token based authentication is properly implemented in your application.

-   _Keep it secret. Keep it safe._  The signing key should be treated like any other credentials and revealed only to services that absolutely need it.
-   _Do not add sensitive data to the payload._  Tokens are signed to protect against manipulation and are easily decoded. Add the bare minimum number of claims to the payload for best performance and security.
-   _Give tokens an expiration._  Technically, once a token is signed – it is valid forever – unless the signing key is changed or expiration explicitly set. This could pose potential issues so have a strategy for expiring and/or revoking tokens.
-   _Embrace HTTPS._  Do not send tokens over non-HTTPS connections as those requests can be intercepted and tokens compromised.
-   _Consider all of your authorization use cases._  Adding a secondary token verification system that ensure tokens were generated from your server, for example, may not be common practice, but may be necessary to meet your requirements.


**Interview Questions**
- What is JWT ?
- Explain JWT Token?
- What do you mean by JWT & How to configure it ?
- Explain JWT token component?
- Diff types of Algorithm for Header?
- What is Payload? 
- What is Signature component in JWT?
- How to generate JWT?
- How to validate JWT token ?
- What is RFC 7519?
- What is Auth0?
- How JSON WEB TOKEN works?
- Explain JWT workflow.
- What is Bearer?
- Diff between Authorization & Authentication? What is JWT Authorization ot Authentication?
- Why to Use JWT?
- Advantages of JWT?
- Where to store JWT Token?
- Create & Verify Jwt Token?
- What is Sign & Verify in JWT ?
- What is iss, iat, sub?
- What is Expiration time in JWT?
- How to refresh JWT?
- What do you mean by Invalidate JWT?
- Explain Ways to invalidate JWT?
- Which npm package to install in order to use JWT?
- What is a Hashing function?


Study Url: 
https://www.freecodecamp.org/news/securing-node-js-restful-apis-with-json-web-tokens-9f811a92bb52/
https://hackernoon.com/restful-api-design-with-node-js-26ccf66eab09
