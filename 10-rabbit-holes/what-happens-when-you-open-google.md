# What happens when you open Google?

Opening a search engine in a browser looks like one action, but it involves many components. The exact path depends on your device, browser, network, and the service's current design.

1. The browser parses the address and checks whether it already has useful cached data.
2. If necessary, the device uses [DNS](../04-internet/dns.md) to find an address for the domain.
3. The browser connects to a server over the internet using [IP](../04-internet/ip.md) networking.
4. It establishes a protected [HTTPS](../04-internet/https.md) connection and verifies the site's certificate.
5. It sends an [HTTP](../04-internet/http.md) request for the page.
6. Servers may route the request through services that handle traffic, application logic, and data.
7. The browser receives a response, downloads any additional resources it needs, and renders the page.

When you submit a search, the browser sends another request containing the query and possibly other context. The service processes it and returns results. Cookies or other browser storage may help preserve preferences or a signed-in session.

This is a simplified journey: caching, content delivery networks, and service architecture can change which systems participate. See [servers](../08-cloud-and-deployment/server.md), [APIs](../05-apis/what-is-api.md), and [how a login works](how-a-login-works.md).

## Curiosity question

When you enter `google.com`, how does your computer find another computer somewhere in the world?

## Explanations guided by the seven questions

### Rabbit hole: How does a computer find another computer after entering `google.com`?

The browser needs a destination to establish a network connection. DNS supplies addresses; routing carries packets toward the destination. The resolver looks up records, then routers forward packets hop by hop. Across the device, local network, internet providers, and service infrastructure. Name resolution and connection happen when no suitable cached connection exists. Browser, DNS resolver, routers, network operators, and destination servers participate. DNS or routing changes can send the request to different service endpoints.
