# Picture Serving subsystem

## General

I think that, to serve profile pictures, we store images in the server's filesystem (encryption?) in a flat directory, with the image named after the user, ex" `jmellington.png`. All pictures are accessed via a GET to `/api/images/{username}.png` but we have a request guard in place so that only authorized users can access it. If an unauthorized user attempts to access it, return a screen grab from never gonna give you up.

## Authorization

A user is, of course, always allowed to access their own photo, where it get complicated is when we let other users see it. My thought is to have a database field for the *requesting* user which specifies a lift of other users' images that they are permitted to access. This permission will be granded by walkwizard and will be automatically revoked when the rating stage of the walk completes. 
