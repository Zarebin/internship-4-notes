# API crowd sourcing app

- django
- drf
- documentation
- load test (locus)
- test
- ...

Eeach question should be answerd by X users.
The correct answer:
Agreements measure how often user's answers align with those from other users. Points awarded for each agreement vary across tasks.


    U1 U2 U3 U4 U5 U6 U7 U8 U9 U10
Q1: 1  1  1  1  0  1  1  0  1  0
Q2: 0  0  0  0  0  1  1  0  0
Q3: 1  1  1  1  0  1  1  1  1 
Q4: 1  1  1  0
Q5: 1  1  1
Q6: 1  1
Q7: 1   
Q6: 0   



## definition
We have a crowdsourcing app like [googlecrowd](https://crowdsource.google.com/). And each one of you should implement 2
APIs. I recommend to install [APK](https://play.google.com/store/apps/details?id=com.google.android.apps.village.boond&hl=en_US&gl=US) to explore more APIs. 

## APIs
### /api/food_fact/

#### GET /food_fact/
- input
 - `user_data` which is sent through header
- response
 ```json
  {
    "image_link": "",
    "question_text": "",
    "cert_text": "",
    "id": 124
  }
 ```

#### POST /food_fact/
- input
```json
    {
        "label": "0(Yes)/1(No)/2(Not sure)/3(skip)",
        "question_id": 124
    }
```
Note: user_data is sent through HTTP Headers

- respose
 201 [No respose]

#### POST /report/
This api is used to report questions by users.
in:
out:

