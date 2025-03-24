Java Brains – Java Backend Bootcamp
Y2K Problems, .com bubble → unemployment

Value ↑ → Ability to be a good Software Engineer
→ Taking tools out here to solve real problems

Bootcamp → not just for better interviews → but for better backend apps
(and that is compulsory)
→ APIs: write apps ← solve problems ← Software Engineer

After backend, go for frontend stuff on the channel

Need-based vs Curriculum learning
→ GitHub link = curriculum + website

Java Backend Engineer
Build Java backends

Applications that run as a server

Exposing APIs for use by frontend developers


+----------------+
| Front-end tier |   ← UI-related
+----------------+
        ↑
        ↓
+----------------+
|   Mid-tier     |   ← What you write as a Java backend engineer
+----------------+
        ↑
        ↓
+----------------+
|   Data tier    |   ← Database
+----------------+

Now (Modern Web Architecture)
Fig. 2: Basic Architecture
Browser
   |
   v  (Page Load)
  CDN ----------------------------+
   |                             |
   v                             |
Backend Server <--- REST Call ---+
       |
       v
    Database
	
User (in browser) makes a request not to the front-end but to a CDN.

Most modern web apps are single-page apps (SPAs), distinct from the traditional Java stack.

The CDN returns a page or JS files, which then make API calls to the backend server.

Key Points:
The front-end now runs on the user’s machine (browser). Earlier, it used to be rendered by the server.

JS code makes API calls, receives API responses, processes the response, and renders it in the browser.

A backend engineer:

Implements APIs

These APIs are often called by JS code running in the user's browser.

                    +---------+
                    | Browser |
                    +----+----+
                         |
                    Page Load / REST Call
                         |
         +---------------+-----------------+
         |                                 |
      +--v--+                         +----v----+
      | CDN |                         | API Gateway |   ← A facade for the frontend
      +-----+                         +-----+------+
                                           |
                     +----------+----------+----------+
                     |          |          |          |
                 +---v---+  +---v---+  +---v---+
                 |Service|  |Service|  |Service|
                 |   A   |  |   B   |  |   C   |
                 +---+---+  +---+---+  +---+---+
                     |          |          |
                 +---v---+  +---v---+  +---v---+
                 |Database| |Database| |Database|
                 |   A    | |   B    | |   C    |
                 +--------+ +--------+ +--------+


Key Points:
Every service has its own database.

Earlier: Only a load balancer with multiple copies of backend servers.

Now: A Load Balancer + API Gateway setup:

Acts as a central coordinator

Provides abstraction to the backend

Example:

Typing a URL (e.g., www.amazon.co.uk) hits a CDN and loads a page.

CDN (Content Delivery Network)
Distributed servers that deliver web content to users based on their geographical locations.

Examples: AWS CloudFront, Cloudflare

Routing:

Requests are routed to the server closest to the user, not the origin server.

Terminology:

Origin Server ⇄ Edge Server

Caching Behavior:

On the first visit → content is served from the origin server

On subsequent visits → content is served from CDN cache


CDN Flow and DNS Resolution
How it works:

The browser sends a request to DNS servers to resolve the domain name of the URL to its corresponding IP address.

Example:
User types: www.javabrains.io
→ Browser sends request to DNS Server
→ DNS resolves and maps www.javabrains.io to an IP address
→ Returns the IP address of the closest CDN edge server

Browser sends a request to the CDN edge server

The CDN edge server checks its cache:

If found → returns the cached version

If not found → sends a request to the origin server

The origin server returns the requested content to the CDN edge server

The CDN edge server stores it in cache

The CDN edge server returns the content to the browser

Content returned includes:

Static content (e.g. HTML, CSS, assets, images, JS, fonts)

Terminology
Edge Locations → Locations where static content is served

Edge Servers → End servers which are interfacing with the request

CDN Providers:

Akamai

Enterprise CDN

Other Notes:
CDN is secure behind HTTPS

CDN providers run and manage CDN and also DNS routing

Cloudflare outage (example note on CDN vulnerability)

