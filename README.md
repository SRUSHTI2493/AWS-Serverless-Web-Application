# AWS-Serverless-Web-Application

## OVerview
Associated with MANSCHAFT IT PVT LTDAssociated with MANSCHAFT IT PVT LTD
Designed and implemented a serverless web application on AWS using Lambda, Amplify, DynamoDB, IAM, and API Gateway. The application serves a static HTML file, leverages serverless functions to interact with a DynamoDB database, and enforces secure access control with IAM policies.

<img width="490" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/c958a8ae-ee3b-40b0-b66e-b25737aead7f">

### Output will get

<img width="396" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/7ced1bec-e15e-4f57-ab4b-8b3fe1e1d9c2">

### what do we need ??

🔹 A way to create/host a webpage

🔹 A way to invoke the math functionality

🔹 A way to do some math

🔹 Somewhere to store/return the math result

🔹 A way to handle permissions

🔹 A text Editor (e.g Notepad++, Notepad, etc)

🔹  An AWS account and access to the Console

🔹  Basic Knowledge of AWS

<img width="506" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/81a5cdd7-8ee1-47fe-932f-27981ad3435a">

**Step-1** Create one folder in Any drive 

**Step-2** in that folder create one HTML file

<img width="577" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/bc1c469d-ebf8-4057-bfec-a67b194b2182">

```
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>To the Power of Math!</title>
</head>

<body>
    To the Power of Math!
</body>
</html>

```

**Step-3** Login to your console

<img width="932" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/a11b423f-e650-4eb8-948f-a0435833f094">

**Search for Amplify**

<img width="956" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/96d8102e-468f-49ea-9e5c-31ff37b72c51">

**Step-4** Click on Get started

**Step-5**  Select Host your web app

<img width="928" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/720d2394-9907-4293-b1e6-8489fca1547d">

**Step-6**  Select Deploy without git provider

<img width="947" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/1a7173ee-9ddd-4e07-80d1-641ba3a0eb3d">

**Step-7** Enter your app name and insert your HTML file here -> save 

<img width="653" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/1c938482-9ed5-470b-97fb-abceb2d6ff52">

**Step-8** open domain link in another app

<img width="670" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/29a0fa63-a0c8-4920-bbb5-f9618af30b68">

**step-9** Now you can see this on your screen

<img width="337" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/02328c6c-8f8f-4796-bf1e-6f0c28447b81">

# Now we Navigate to Lambda

<img width="590" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/fd5f1a81-a6a4-4cfe-a43b-8bc45110b5f5">

***open in new tab***

**Step-1** Create new Function

<img width="923" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/c676bd68-979d-4e59-96ae-172d90f2e5a4">

**Step-2** Enter function name -> enetr Runtime(python) -> select Architecture -> and last Click on Create Function

<img width="950" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/417bd72c-6c0b-45b5-87e1-4d33ab1c13f8">

**Step-3** In test section modify this code from my lambda-orginal file and save that code (cntrl+S)

```
# import the JSON utility package
import json
# import the Python math library
import math

# define the handler function that the Lambda service will use an entry point
def lambda_handler(event, context):

# extract the two numbers from the Lambda service's event object
    mathResult = math.pow(int(event['base']), int(event['exponent']))

    # return a properly formatted JSON object
    return {
    'statusCode': 200,
    'body': json.dumps('Your result is ' + str(mathResult))
    }

```

<img width="917" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/913f7925-20a1-49c9-b925-20f766ecce84">

**Step-4** configure test event

<img width="901" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/cc80165b-694a-4523-8207-95870092a5f4">

**Step-5** Enter event name -> select Event sharing settings (Private) -> edit below code in Even JSON -> save

```
{
  "base": 2,
  "Exponent": 3
 
}

```

<img width="731" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/aed4d2e1-9b7d-4986-ba46-b082f9b1714c">

**Step-6** click on TEST button and see below outout

<img width="623" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/1b560cd4-871a-411d-9a12-78ebda1c880f">

# Now we naviagte to APIGateway

<img width="617" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/38d3fc51-9f55-4433-850f-0c737fc9c4be">


