# iOS 9 ATS (App Transport Security) exceptions for common third-party services

> App Transport Security is a feature that improves the security of connections between an app and web services. The feature consists of default connection requirements that conform to best practices for secure connections. Apps can override this default behavior and turn off transport security.  
> Transport security is available on iOS 9.0 or later, and on OS X 10.11 and later.

Source: https://developer.apple.com/library/prerelease/ios/technotes/App-Transport-Security-Technote/

## What does that mean?

That unless you change something in your iOS app' plist, your app will not be able to communicate with unsecure HTTP servers, when it runs on iOS 9.

That's a good thing really; Apple is trying to force people to update their HTTP servers to use the latest HTTPS protocols & recommendations: TLS 1.2, SHA256 or better, forward secrecy.

## OK. A good thing. What's the problem then?

Where this could cause you issues is if you use third-party services that have not yet adhered to those standards.

They might have a good reason not to (doubtful!), or they are working on implementing them, but are not there yet.

## What's the solution?

Right now, the best workaround is to whitelist all servers on a case-by-case basis, per the service providers own recommendations.  
Thus the need for the list in this repository.

In the ats.plist file in this repo, you'll find the exceptions that you need to add to your app .plist, if you use some of the third-party services that published recommendations regarding ATS.

## How can I help?

If you know of any other services that published recommendations for exceptions that should be used in iOS 9 apps, for their service to work as expected, please fork and create a pull request.

