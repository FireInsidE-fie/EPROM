---
tags:
  - framework
---
OAuth is a **security framework allowing a user to sign in using an external service**, such as Google, or GitHub.
The external service is tasked with the **authentication part of the login flow**.
# Glossary
## Authorization Server
An Authorization Server is **the external service authenticating your user** and obtaining authorization.
Authorization in this case is usually obtained by **prompting your user for their consent**.
Once authorization has been obtained, the authorization server **issues access tokens to your application**.
## Resource Server
A resource server **hosts protected resources, typically [[HyperText Transfer Protocol]] endpoints**, and require an access token as a credential for requests.
As an example, this would be your protected routes in your application: profile, friends, create/deleting records, etc.
Or, in Facebook's case, the "Graph API".
## Client
Your application **is an OAuth client**.
The client **requests authorization for a given user, and, if granted, uses the issued access token to access protected resources**.
## Resource Owner
**The user** is referred to as the resource owner. It is an entity capable of **granting access to a protected resource**.
For social networks, this would be the posts and pictures the user posted, and which are being accessed.
In enterprise environments, this would be company data.
# Protocol Flow
Grant types, otherwise called *flows*, determine what the OAuth client, or application, has access to on the service.
Here is the base authorization code flow:
1. The application **requests authorization from the user** by redirecting the user to the authorization server.
2. The authorization server **authenticates the user and obtains their consent**, permitting the application to access protected resources via an API.
3. The authorization server **redirects the user back to the application** with an authorization code, which represents the authorization obtained from the user.
4. The application **exchanges the authorization code for an access token**.
5. The application **uses the access token to request protected resources**.
Once the resources have been extracted from the resource server, the application is free to do as it wishes.
The OAuth part of the flow ends here, as its job was just the authorization and retrieval of information.
# Resources
- [Passport Library's OAuth Explanation](https://www.passportjs.org/concepts/oauth2/)
  Great conceptual and practical overview!
- [Passport's Practical Explanation of the Login Flow](https://www.passportjs.org/concepts/oauth2/authorization/)
  Explaining what happens at each step, from login to authorization to callback.