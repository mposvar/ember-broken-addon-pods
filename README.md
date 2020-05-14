# ember-broken-addon-pods
bug demo

Repro Steps:
1. Clone Repository
2. Install lerna, ember (if necessary)
3. In root repository folder > `npx lerna bootstrap --hoist`
4. `cd packages/host-app`
5. `ember s`
6. Go to http://localhost:4200

For each type of component, it should Output:


```
<h1>{Component Description}<h1>

<p>Internal Component Content</p>

<p>Yielded Content</p>
```


except for the pod structure - glimmer component defined in the addon. It does not yield the Internal Component Content


Seemingly
MyAddonComponent (Addon, Pod Structure) does not render it's internal template, but does render the yielded block
MyAddonComponentB (Addon, Classic Structure) does render it's internal template, and does render the yielded block.
MyHostComponent (Host, Pod Structure) does render it's internal template, and does render the yielded block.
