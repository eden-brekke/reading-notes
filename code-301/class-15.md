# Readings: Authentication
Below you will find some reading material, code samples, and some additional resources that support today’s topic and the upcoming lecture.

Review the Submission Instructions for guidance on completing and submitting this assignment.

## Reading
[What is OAuth](https://www.csoonline.com/article/3216404/what-is-oauth-how-the-open-authorization-framework-works.html)

* What is OAuth?
  * OAuth is an open-standard authorization protocol that shows how unrelated servers and services can allow authenticated access to their assets without sharing credentials 
* Give an example of what using OAuth would look like.
  * When you go to log onto a website and you click a button that's linked to another website, the other website authenticates you. 
* How does OAuth work? What are the steps that it takes to authenticate the user?
  1. First the site connects you to a second site on behalf of the user
  2. Second the site generates a one-time token
  3. The first site gives this token to the user's client software
  4. The clients software presents the request token to the auth provider
  5. If not already authenticated to authorization provider, the client may be asked to authenticate, then the client is asked to approve it to the second site
  6. User approves the transaction at the first site
  7. user is given an approved access token 
  8. user gives approved access token to first site
  9. first site gives access token to second site as proof of authentication
  10. second site lets first site access their site
  11. user sees success!
* What is OpenID?
  * OAuth is about authorization and OpenID is about authentication. OpenID is for humans logging into machines and OAuth is for machines logging into machines on behalf of humans. It's now used as an authentication layer for OAuth

[Authorization and Authentication flows](https://auth0.com/docs/get-started/authentication-and-authorization-flow)

* What is the difference between authorization and authentication? <br>

|Authentication|Authorization|
|:---:|:---:|
|Determines whether users are who they say they are|Determines what users can and can't access|
|Challenges user to validate creds|Verifies whether access is allowed through policies/rules|
|Usually done before authorization|Done after successful authentication|
|Transmits info through ID token|Transmits info through Access Token|
|Governed by OpenID|Governed by OAuth|
|Example: Employees are required to authenticate through network before accessing company email| Example: After Authentication system determines what info employees are allowed to access|
* What is Authorization Code Flow?
  *  Authorization code grant type is used to obtain both access and refresh tokens, optimized for confidential clients. and is a redirection based flow. client must be capable of interacting with resource owners useragent and capable of receiving incoming requests
* What is Authorization Code Flow with Proof Key for Code Exchange (PKCE)?
  * PKCE is a security extension for public clients to avoid malicious programme creeping into your computer  
* What is Implicit Flow with Form Post?
  * an alternative to the Authorization code flow, intended for public clients, often used with form post response mode. 
* What is Client Credentials Flow?
  * the client can request an access token using its client credentials when the client is requesting access to protected resources. Authorization server sends back an access token to client 
* What is Device Authorization Flow?
  * Device authorization flow contains two paths, one occurs on the device requesting authorization and the other occurs in the browser. Browser flow-path has the device code inbound to the session in the browser and occurs in parallel to part of the device flow path
* What is Resource Owner Password Flow?
  * Highly trusted applications use Resource owner password flow, it requests that users provide credentials typically using an interactive form. Because the credentials are sent to the backend they can be stored for future use before being exchanged for an access token, it's imperative that the application is absolutely trusted with this info. 

## Additional Resources

### Bookmark/Skim
[Auth0 for single page apps](https://auth0.com/docs/libraries/auth0-react)



## Things I want to know more about
  Curious how we implement OAuth to the sites we've been creating, can you create a cache specifically for each user? I imagine you can, is that just cookies? I still feel kinda nooby when it comes to this stuff :P 