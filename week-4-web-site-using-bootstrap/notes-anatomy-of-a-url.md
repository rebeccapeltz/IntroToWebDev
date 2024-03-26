# Notes: Anatomy of a URL

<figure><img src="../.gitbook/assets/image (2) (1).png" alt=""><figcaption><p>Noting the parts of a URL</p></figcaption></figure>

### Universal Resource Locator

URL is an acronym for Universal Resource Locator.  It is made up of different parts.  The example above shows the unique parts of a URL  that route us to an HTML file stored on GitHub.

There are three distinct parts to this URL.

* protocol
* domain name
* path

All URLs have these parts.  There are a couple more parts that we aren't using in this URL.  We don't see the port or any parameters.   An example of a URL with a port and parameters is shown below.  In this example, the parts are:

* Protocol: `http://`
* Domain name: `localhost`
* Port: `8080`
* Path:  `/search`
* Parameters: `?q=cats`

```html
http://localhost:8080/search?q=cats
```

When no port is specified as in the GitHub URL, the default port, 80, is used.  If there are parameters in the URL, they always follow the path and start with a `?`.  There is only 1 parameter in the example above.  The parameter name is `q` , and the value is `cats`.  There can be multiple parameters in a URL. There are no parameters in the GitHub URL.

### Protocol

URLs request data from servers. The protocol **https://** contains the acronym HTTP, so it sends hypertext markup language to the server. The s at the end of HTTP tells the server this is a secure version of HTTP.

### Domain Name

A web page sends and receives data from all over the internet.  The internet requests contain a domain name that is looked up for by a Domain Name Server.  The Domain Name Server will find an IP Address for that server.  Routing between servers is done with IP addresses. &#x20;

You can find your IP address if your computer uses a Wi-Fi connection. &#x20;

To find your IP address on Windows, Press the Windows key, choose **Settings | Network & internet | Wi-Fi**, and click on the active Wi-Fi connection. Scroll to the bottom to see the IPv4 address.

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption><p>Finding your IP addrss on a Mac</p></figcaption></figure>

To find your IP address on a Mac: From the Apple icon on the top left choose **System Settings | Network | Wi-Fi | Details.**  The IP address is your connection, which is how your router would find you to send and receive data.

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption><p>Finding your IP address on Windows</p></figcaption></figure>

### Path

Once the Domain name has been transcribed to an IP address, it can be located on the internet.  The path will direct the request to a location associated with the IP address on the server.  Depending on the type of request the server will get information based on the path and return it to the browser.

