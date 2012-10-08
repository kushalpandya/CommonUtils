# CommonUtils

CommonUtils is a utility library for Java which provides common set of functionalities that are required in most of the web applications. Functions include, plaintext/file to hash-code generation, validating form fields, generating random [CAPTCHA](http://en.wikipedia.org/wiki/CAPTCHA) challenges, and many other stuff.

## Why CommonUtils?

I've been working on many Java web projects lately, and required these common set of functionalities in each of them, so I created this library for my usage, but its free and open source under terms of [GPLv3](http://www.gnu.org/licenses/gpl.html) so anyone can add new features to this and make it better.

## Platforms, Tools and Technologies used

* **IDE** - Eclipse 4.2
* **Java** - JDK 1.7 (to be available for JDK 1.6 too)

## Package Description

* `org.commonutils.util` - Classes for Form field validation and Mathematical CAPTCHA generation.
* `org.commonutils.security` - Classes for Forward Hash code generation ([MD5](http://www.ietf.org/rfc/rfc1321.txt) and [SHA-1](http://www.ietf.org/rfc/rfc3174.txt), for now).

## Author

[Kushal Pandya](https://github.com/kushalpandya)