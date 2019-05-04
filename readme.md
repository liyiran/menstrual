
# Backend Challenge

## Grading
The challenge will be evaluated on:
* proposed solution and documentation
* appropriate use of git
* testing
* coding standards
* documentation around possible improvements or different approaches

## Context
Users track symptoms in their menstrual cycle via an app. 

The challenge is to create a service that receives these events and uses them to determine the running average menstrual
cycle length of all menstrual cycles of all users. Use these rules for defining a cycle:

* Period phases are consecutive bleeding days (days with any type of bleeding). 1-day-long period phases are possible.
* A cycle starts every time a period phase starts, and ends at the beginning of the following period phase.

The service will provide the following endpoint to receive individual track events:

````
POST /events

{
  "user_id": 123456,
  "symptom": 3,
  "timestamp": "2017-04-23T18:25:43.511Z"
}
````

The possible symptoms are:

| SYMPTOM ID  | SYMPTOM         |
| ----------- | --------------  |
| 1           | light bleeding  |
| 2           | medium bleeding |
| 3           | heavy bleeding  |
| 4           | increased focus |
| 5           | cramps          |
| 6           | tender breasts  |

The service will also provide the following endpoint which enables querying for the current average cycle length:

````
GET /cycles/average

````

and the response should be

````
{
  "average_cycle": {
    "length": 28.1 
  }
}
````

We are conscious of your time. It's fine if you need to skimp on some aspects to save time - mention your decisions in your README. The aim is we get an idea of your coding style and level, as well as how you go about designing backend systems. We will use this exercise as a basis for further discussion in the interview process.

Thank you for your time, feel free to ask questions, and we would also appreciate any feedback on how to improve the challenge for the future.
