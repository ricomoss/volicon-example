Uplynk Slicer APIs
==================

The Uplynk slicer has built-in functionality as a HTTP webserver.  This allows users to make HTTP calls to it trigger certain functionality.   

To see more information about possible APIs: http://support.uplynk.com/doc_live_slicer_api.html

Calling APIs
============

Notes
-----
- The `liveslicer` needs to run uninterrupted to function.  All API calls must be made from a different process.


Inserting Ad Break
------------------

1. Using `curl` we can call the slicer `/pod_start` API to start ad breaks.

        ➜  ~ curl http://127.0.0.1:65009/pod_start   
        {
           "error" : 0
        }

2. Using `curl` we can call the slicer `/pod_end` API to end ad breaks.

        ➜  ~ curl http://127.0.0.1:65009/pod_end  
        {
           "error" : 0
        }

Notes
-----

- The delay of a "live stream" is around 60 seconds.  You will see the result of your ad breaks in your channel approximately 60 seconds after you've inserted them.

- In order to make the Uplynk system insert ads where you've added ad breaks, you'll need to add a GET parameter to the URL.  `ad=dummy`

Inserting Boundaries
--------------------

1. Using `curl` we can call the slicer `/boundary` API to insert a boundary with GET parameters.

        ➜  ~ curl 'http://127.0.0.1:65009/boundary?type=test&expected_duration=15'
        {
           "error" : 0
        }
        
Notes
-----

- Notice the GET parameter key `type`.  The value for this key will be the *name* of the boundary.

- In order to manipulate boundaries you'll need more GET parameters in the playback URL.  See documentation for futher instructions: http://support.uplynk.com/doc_live_slicer_api_boundary.html
