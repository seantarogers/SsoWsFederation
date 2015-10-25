SsoWsFederation
===========================

A single sign on/sign off prototype implemented with Windows Identity Federation and Asp.Net Mvc.

Overview
------

A single sign on/sign off prototype implemented with Windows Identity Federation/WsFederation and Asp.Net Mvc.

To run this solution
------

1. Please create a self signed certificate and place it in the personal store on your machine. 
http://msdn.microsoft.com/en-us/library/bfsktky3%28v=vs.110%29.aspx
Note the CertificateManager.cs currently looks for a cert named = "SeansCert" in personal store.

2. Add the certificate thumbprint to the asax of the relying parties.

Interesting areas of code
------

1. Domain specific claims enrichment via the Claims authentication Managers on each RP ensuring the tokens do not become too bloated.
2. Scalable Sign sign out using the realm tracker to only sign you out of sites you have visited.
3. And many others!
