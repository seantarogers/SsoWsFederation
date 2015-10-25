SsoWsFederation
===========================

A single sign on/sign off prototype implemented with Windows Identity Federation and Asp.Net Mvc.

Overview
------

Todo...


To run this solution
------

1. Please create a self signed certificate and place it in the trusted people store on your machine. 
http://msdn.microsoft.com/en-us/library/bfsktky3%28v=vs.110%29.aspx
Note the CertificateManager.cs currently looks for a cert named = "seansatcert" in trusted people.

Interesting areas of code
------

1. Invoking SignalR .Net client from inside NServiceBus consumer to chain together a push notification back to the browser
2. Custom OWIN middleware to authenticate the custom Certificate Token.
3. Interception of the SignalR connection messages to swop out the OAuth token from the cookie into the Authorization header of the Http request (because the OAuthMiddleware expects the tokens to be there).
4. Async OAuth Token provider implementation.
5. And many others!

For more information
------

Please see the architectural diagram pdf in the root of the solution
