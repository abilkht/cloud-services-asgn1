## Overview

A popular use of cloud services is to manage media that is uploaded
from devices. This assignment will create a basic application
for uploading video to a cloud service and managing the video's metadata.


HTTP API:
 
    GET /video
   - Returns the list of videos that have been added to the
     server as JSON. The list of videos does not have to be
     persisted across restarts of the server.
     
    POST /video
   - Returns the JSON representation of the Video object that
     was stored along with any updates to that object made by the server. 
   - **_The server should generate a unique identifier for the Video
     object._** 
     
    POST /video/{id}/data
   - The endpoint should return a VideoStatus object with state=VideoState.READY
     if the request succeeds and the appropriate HTTP error status otherwise.
     
    GET /video/{id}/data
   - Returns the binary mpeg data (if any) for the video with the given
     identifier. If no mpeg data has been uploaded for the specified video,
     then the server should return a 404 status code.
