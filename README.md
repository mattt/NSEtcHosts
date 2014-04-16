# NSEtcHosts

NSEtcHosts uses `NSURLProtocol` to intercept requests for specified host names, resolving them instead to a different IP address, similar to an [`/etc/hosts` file](http://en.wikipedia.org/wiki/Hosts_%28file%29) on a Unix system.

> This is a proof-of-concept, and is not intended for use in production.

## Usage

```objective-c
[NSURLProtocol registerClass:[EtcHostsURLProtocol class]];
[EtcHostsURLProtocol configureHostsWithBlock:^(id <EtcHostsConfiguration> configuration) {
    [configuration resolveHostName:@"google.com" toIPAddress:@"98.138.253.109"];
}];
```

![NSEtcHosts in Action](https://raw.githubusercontent.com/mattt/NSEtcHosts/screenshots/screenshot.png)

```objective-c
NSURL *URL = [NSURL URLWithString:@"http://google.com"];
[webView loadRequest:[NSURLRequest requestWithURL:URL]];
```

## Contact

[Mattt Thompson](http://github.com/mattt)
[@mattt](https://twitter.com/mattt)

## License

NSEtcHosts is available under the MIT license. See the LICENSE file for more info.
