# \<gun-client\>
Element to use with GUNDB (http://gun.js.org/enterprise/)

Provides an easy starting point for a Gun based application.
- loads gun.js
- switch plugins on/off through attributes
  (each,local,image please see https://github.com/amark/gun/wiki/Snippets-(v0.3.x) )
- set peers through attribute `server-url`
- initialises Gun with a global `var gun`.
- publishes a `gun-loaded' message to the rest of your application (uses `<iron-signals>` )

## Examples:

Default (No peer,no syncing):

    <gun-client></gun-client>


One peer:

     <gun-client server-url="http://yourServer.com/gun"></gun-client>

Multiple peers:

     <gun-client server-url="http://server1.com/gun, http://server2.com/gun"></gun-client>

Switch on 'each' plugin https://github.com/amark/gun/wiki/Snippets-(v0.3.x)#guneach:

      <gun-client each></gun-client>
