# ember-broken-addon-pods
bug demo

Repro Steps:
1. Clone Repository
2. Install lerna, ember (if necessary)
3. In root repository folder > `npx lerna bootstrap --hoist`
4. `cd packages/host-app`
5. `ember s`
6. Go to http://localhost:4200

You should see, in order:

Apple!
Banana

Cow!
Horse

Truck!
Car

Instead, you see:

Banana

Cow!
Horse

Truck!
Car

Seemingly
MyAddonComponent (Addon, Pod Structure) does not render it's internal template, but does render the yielded block
MyAddonComponentB (Addon, Classic Structure) does render it's internal template, and does render the yielded block.
MyHostComponent (Host, Pod Structure) does render it's internal template, and does render the yielded block.
