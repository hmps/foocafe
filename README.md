FooCafé JSPM Demo by Apsis
==========================

At [Apsis](http://www.apsis.com) we use [JSPM](http://www.jspm.io) as our front-end package manager. We have set up our own registry, on our own servers, that allow us to stay inside the company walls, but with all the benefits of a proper package manager.

Our front-end structure is now completely component based and every component is a package, ready to be consumed via JSPM.

This allows us to version control each component on its own, and each implementation to have full control over its own dependencies. When a component gets updated it is up to the developer working on the implementation to decide wether to update to the new version on not.

# Running this demo
1. Clone this repo
2. Run `$ npm install`. That will install JSPM and kick off a `jspm install` once it is done.
3. Point a server to the root dir and test it out.
*We love [live-server](https://github.com/tapio/live-server) and use it all the time for tasks like this.*

# Usage in real life
When an implementation requires a specific component, all the developer has to do is to install it via JSPM:

```
$ jspm install apsis:modal
```

And import it into the script running on the page in question:

```js
import { modal } from 'modal';

// Do something with modal, e.g. open it.
modal.open({ title: 'Alert' });
```

### Running your own JSPM registry
We us [JSPM Git](https://github.com/Orbs/jspm-git) be able to use our own git servers as a registry for JSPM.
