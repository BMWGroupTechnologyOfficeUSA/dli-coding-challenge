# Coding Challenge

## Problem Description

Modern vehicles are no longer on their own when driving on the road but are part of a large connected fleet and we need scalable systems to transmit observed data from cars, process it online, and then deliver relevant data to appropriate cars across the globe.

In this challenge, assume that each car is equipped with a camera that detects road signs and sends them to a back-end server over the internet. The back-end server stores the observations, learns existence and positions of road signs from these observations and upon request delivers a list of these learned road signs to other vehicles as they approach the area. 

The vehicle will use this information to display the presence of upcoming road signs to the driver.


## Challenge Overview

Implement a web service that can receive road sign observations. A road sign observation is defined by the following attributes:

- **latitude**: double  
- **longitude**: double  
- **type**: enum (e.g. *SPEED_LIMIT_30*,
*PASSING_RESTRICTION*)

Please design and implement a REST web service that is capable of receiving one observation at a time. 

The received observation shall be stored internally on the back-end server. Persistent storage of these observations is not required. 

The web service shall be used to provide vehicles with road signs for a given location. Since your fleet might report the same sign multiple time, it will send you multiple observations of the same sign. When requesting nearby signs, the vehicle shall be able to provide a latitude and longitude position together with a radius in which road signs shall be searched and returned. In this search radius, at most one instance of a **type** shall be returned (e.g. 5 *SPEED_LIMIT_30* signs were reported; only 1 shall be returned). The web-service shall be able to serve all recognized road sign types to a requesting vehicle.


## Design Guidelines

Please follow these design guidelines:

- Your solution has to include both front-end and back-end.
    - Your back-end solution has to use the paradigms of REST and the Node.js framework.
    - Your front-end needs to be a web page written in JavaScript and HTML that can submit raw data to the server as well as display appropriate data from the server.  
- Deploy the web service (e.g. on Amazon EC2, Heroku, Google AppEngine).

## Extensions

Feel free to pick from the following extensions to extend your solution, but they are not required:

- Implement persistence for your observations using a database of your choice.
- Implement a client that shows the clustered signs in a map view upon request.
- Implement a standard authentication mechanism for your REST interface and describe how to use it. 

## Guidelines for Submission

Your submission shall contain the following:

- A README.md with a description of the problem and your solution.
- All source code. Package the source files into a zip archive or provide a link to a hosted repository for example on GitHub.
- A link to the client application that is live and functional.

## Evaluation Criteria

This assignment helps us to get insights into your style of software engineering and coding. It is essential to write good quality code that can easily be understood or extended by other developers. We expect your web service to return a meaningful result. 
