# NSEtcHosts

> This project was a proof-of-concept that relied on a combination of factors unique to the time of creation 
> that have since been remediated by, among other things,
> the ubiquitous adoption of HTTPS, iOS App Transport Security, and `NSURLSession`.
> Insofar as this approach should ever have been used (it shouldn't)
> the aforementioned improvements to the networking stack render this project inviable.
> Suffice to say, this project is no longer maintained.

NSEtcHosts uses `NSURLProtocol` to intercept requests for specified host names, 
resolving them instead to a different IP address, 
similar to an [`/etc/hosts` file](http://en.wikipedia.org/wiki/Hosts_%28file%29) on a Unix system. 
(This does not actually affect the _actual_ hosts file used by iOS, 
nor does it affect routing behavior outside of the application process)

## Usage

```objective-c
[NSURLProtocol registerClass:[EtcHostsURLProtocol class]];
[EtcHostsURLProtocol configureHostsWithBlock:^(id <EtcHostsConfiguration> configuration) {
    [configuration resolveHostName:@"google.com" toIPAddress:@"98.138.253.109"];
}];
```

## Contact

[Mattt](https://twitter.com/mattt)

## License

NSEtcHosts is available under the MIT license. 
See the LICENSE file for more info.
