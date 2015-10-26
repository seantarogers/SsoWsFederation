SsoWsFederation
===========================

A single sign on, single sign out prototype implemented using Windows Identity Federation/ System.IdentityModel/ WsFederation and Asp.Net Mvc.

To run this solution
------

1. Please create a self signed certificate and place it in the personal store on your machine. 
http://msdn.microsoft.com/en-us/library/bfsktky3%28v=vs.110%29.aspx
Note the CertificateManager.cs currently looks for a cert named = "SeansCert" in personal store.

2. Add the certificate thumbprint to the asax of the relying parties.

Interesting areas of code
------

1. Domain specific claim enrichment via each RP's ClaimsAuthenticationManager. These ensure domain concepts do not leak out into the STS and bloat the tokens unecessarily.
2. Scalable single sign out using the Realm Tracker.  This feature enables us to sign a user out of sites that they have actually visited, rather than issuing an inefficient and unscalable blanket sign out of all federated sites.
3. Many others!
