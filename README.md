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

1. Domain specific claims enrichment via the Claims authentication Managers on each RP. These ensure domain concepts do not leak out into the STS and bloat the tokens unecessarily.
2. Scalable Sign sign out using the realm tracker.  This feature enables the system to only sign a user out of sites that they have actually visited. As opposed to an inefficient and unscalable blanket sign out.
3. Many others!
