# apm
## Angular Package Manager

How awesome would it be during development if you could write

```js
angualr.module("app", ['apm://github/angular-ui/angular-ui', 'apm://bitbucket/AwesomeDude/AwesomeDirective'])
```

, and when you refreshed the page you'd be getting those services, directives, etc?

No manual downloading locating and saving. No CLI install commands, then including the script tag, then including as a module as well. Just the last essential step: Should you ask for it, you shall have it.

To me, this seems like client-side dependency-management heaven.

For production we can bundle up the deps for you, or you can use CDN.

***

That is... if we make this. I have 3 main ideas for going about this:

1. Do all the logic client side. (+) Easy, pure client-side JS solution (-) No local caching (-) Might generate some traffic for whoever hosts those deps.
2. Monkey-patch angular.module to try to get these from a locally running server, which goes out, and grabs them for you. (+) Caching (-) Additional run-time dependency
3. Watch the files. When they are saved and a new dep is introduced, go out and put it in a pre-defined location besides the other assets. (+) Caching (-) Additional run-time dependency (-) Watching might be inefficient

Which one do you think would be best, and why?

## Contact

Would you like this to happen? Do you have any ideas, comments, corrections? Want to participate?

Then find me on the [#angularjs IRC room on freenode](http://webchat.freenode.net/?channels=angularjs&uio=d4), usually under the handle Wizek, or [open a new issue here](https://github.com/Wizek/apm/issues). You can also fork+pr.