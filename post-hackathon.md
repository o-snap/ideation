Ideas for post-hackathon changes (other than the obvious of finishing unfinished code)

# Web Infrastructure
There's no reason not to use rocket as both the Web interface server. Move all current rocket dirs to `/api/` and serve html and javascript via roket's templating system to the browser. This will require some changes to the current HTML but not too much. Will simplify overall design and reduce attack surface and number of things that can break. This will also make cookie handling a LOT easier and more secure.

## User logins
Im a dumbass and we shouldn't be hashing passwords client-side. Especially because the salt will be accessable to the curious. It's ok to transmit user login information in the "clear" to the server since we're using tls and we'll hash server-side. This will also reduce website load times and resource footprint (yippee!)

Since we're handling location data, we should protect the user account with 2fa (add totp and use existing sms support)

### oAUTH
Or, better yet, don't have any authentication and make that microsoft's responsibility. Need to look into integrating with WPI's oAUTH SSO. Has the benefit of implicit verification that user is a member of WPI community. check out https://developer.microsoft.com/en-us/identity/add-sign-in-with-microsoft. 

# Maps
Google maps has a great collection of APIs for both web and app-native uses. With a normal account we can make 40k requests per month for free and once we get up and running could apply for non-profit status which would grant us even more. These include distance calculations, routing data, embedding maps etc. 

Apple also has a web mapkit API which might be nice since Apple's better with user privacy but is not as feature-complete.

Potential feature: add option for privacy-concious users to route all maps requests through our server which would anonymize them before sending to Google at the cost of not getting interactive maps. 

# Further steps
For now, I'm happy to run everything on my own servers however if we actually want to launch this, look into AWS hosting and/or cloudflare services. In such a case, we should apply to the school for a grant to cover hosting costs. 

Get all of our code under a licence we can all agree on. I would be happy with GPL3 however some of us might prefer Apache or MIT. Either way, I strongly contend that all of our code should remain FOSS. 

If we do want to handle payments in the future such as if we introduce an uber-esque paid buddy tier, I think we should only function as an escrow between the parties and not collect any fees. 
