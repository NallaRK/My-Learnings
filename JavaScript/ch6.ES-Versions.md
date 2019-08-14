## ES5, ES2015, ES2016 , ES2017, ES.Next

EcmaScript defines standards and provide specs, browsers (JS Engines), implements them and releases with newer browser versions.

Generally browsers takes significant time to implement new EcmaScript specs, so if you use new specs in your applicaiton, it could fail in browsers, where new specs not yet avilable.

So transpilers like Babel, TypeScript, CoffeScript will transpile/pollyfill code to ES5 version or as configured, so that applicaiton can run in old version of browsers.

It is better to use new language features and using Babel/TypeScript to transpile it into ES5 version.
