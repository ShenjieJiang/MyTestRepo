### 1. Do the hands-on practice
Finish the two hands-on practice from [CDN.md](CDN.md) and [DNS.md](DNS.md)

### 2. Draw a infrastructure architecture diagram
Draw a infrastructure architecture diagram for the hands-on that you just did for CDN and DNS. It should include 3 components:
1. the jiangren.com.au website
2. the CloudFront CDN component
3. the Route53 hosted zone

Please reflect following in the diagram:
1. the relationship between above components
    CDN (Content Delivery Network) and DNS (Domain Name System) work together to efficiently deliver content to users across the globe. Here's how they typically interact:

    1. **DNS Resolution:**
    - When a user wants to access a website, they type the domain name (e.g., example.com) into their web browser.
    - The browser initiates a DNS lookup to translate the domain name into an IP address. This is done by querying DNS servers, which hold mappings of domain names to IP addresses.
    - The DNS server returns the IP address associated with the requested domain name to the user's browser.

    2. **CDN Integration:**
    - Many websites use CDNs to distribute their content across multiple servers located in different geographic regions.
    - When setting up a CDN, the website's DNS records are configured to point to the CDN provider's servers instead of directly to the origin server where the website is hosted.
    - When the DNS lookup is performed, the CDN provider's DNS servers return the IP address(es) of the server(s) within the CDN network that is closest to the user's location.

    3. **Content Delivery:**
    - After DNS resolution, the user's browser establishes a connection with the server(s) returned by the CDN's DNS servers.
    - The CDN server(s) then deliver the requested content to the user's browser.
    - The CDN may cache static content like images, CSS files, and JavaScript files on servers located closer to the user to reduce latency and improve load times.
    - Additionally, the CDN may use techniques like edge caching, content optimization, and TCP optimization to further enhance performance.

    In summary, DNS is responsible for translating domain names into IP addresses, and CDNs leverage DNS to direct users to the nearest server within their network, optimizing content delivery and improving website performance.

2. the traffic flow when a user requests your "your_name.jiangrendevops.com" website. i.e. what happens after a user type in "your_name.jiangrendevops.com" website in a browser?
    When a user types in "your_name.jiangrendevops.com" into their web browser and hits enter, several steps occur behind the scenes to serve the requested website. Here's an overview of the traffic flow:

    1. **DNS Resolution:**
    - The user's web browser initiates a DNS lookup to translate the domain name "your_name.jiangrendevops.com" into an IP address.
    - The DNS resolver on the user's device or network queries the DNS servers responsible for the "jiangrendevops.com" domain.
    - The DNS servers respond with the IP address associated with "your_name.jiangrendevops.com". If the domain is using a CDN or load balancer, multiple IP addresses may be returned.

    2. **Establishing a Connection:**
    - The user's web browser uses the returned IP address(es) to establish a TCP connection with the server hosting the website.

    3. **HTTP Request:**
    - Once the TCP connection is established, the user's browser sends an HTTP request to the server for the specific resource requested (e.g., the homepage, an image, or a script file).

    4. **Server Processing:**
    - The server receives the HTTP request and processes it.
    - If the website is dynamic, the server may generate the requested content by executing code (e.g., PHP, Python, Node.js) and querying databases.
    - If the website is static, the server may serve pre-built HTML, CSS, JavaScript, and media files directly.

    5. **Content Delivery (CDN):**
    - If the website is using a Content Delivery Network (CDN), the CDN's edge servers may intercept the request.
    - The CDN determines the optimal server to serve the content based on factors like the user's geographic location, server load, and network conditions.
    - The CDN may cache static content and serve it from edge servers located closer to the user to reduce latency and improve performance.

    6. **HTTP Response:**
    - The server or CDN generates an HTTP response containing the requested content.
    - The response is sent back to the user's web browser over the established TCP connection.

    7. **Rendering the Website:**
    - The user's web browser receives the HTTP response and begins rendering the website.
    - The browser parses the HTML content, processes CSS stylesheets and JavaScript files, and renders the website according to the specified layout and interactivity.

    8. **Displaying the Website:**
    - The fully rendered website is displayed in the user's web browser, allowing the user to interact with the content and navigate the site.

    Throughout this process, multiple network layers, protocols, and technologies are involved to ensure the smooth delivery of the requested website to the user's browser.

You can use [draw.io](https://app.diagrams.net/) to draw this diagram easily. Make sure you save both XML file(.drawio) and the diagram picture file (.png) when you finish, so that you can edit your diagram again in the future.