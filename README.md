# :bookmark_tabs: AWS-Serverless-Web-Application

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

**Step-1** Open APIGateway service -> select to create REST API

<img width="540" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/4f0b2edb-7f0d-40d4-83c6-0273b03f65b2">

**step-2** create API 

<img width="524" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/cde5c4a2-3ddf-4570-b76f-fffcbdf7987c">

**Step-3** so there is no methods on screen , create method -> slect to post in drop down

<img width="541" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/2bc851d8-e86b-464d-9b2b-cc4ef430d9a8">
<img width="527" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/df79a769-e0f5-4d21-8273-b22eedfcc877">

**Step-4** Select integration type-> insert name-> Save

<img width="695" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/a4ac00db-9784-4c04-9e82-578b31bf5170">

**Step-5** In action menu enable CORS -> CLICK on enable CORS-> then click on YES, replace existing value.

<img width="653" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/3aff52dc-85bd-4cae-b389-f889eedca820">
<img width="692" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/3e2270f4-7e68-4039-adac-52435f1270a3">

**Step-6** In action menu select Depoly API -> select Deployment stage and give name and -> Deploy

<img width="668" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/1fdcf4a7-64ee-4c5d-bab8-8a4f9cabf966">
<img width="458" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/7049f0a0-8b1f-4241-aab4-29a712271b1f">

**Step-7** you can get one URL copy that url and paste in notpad.

<img width="688" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/e8c341a6-99d8-49dc-ad6b-68d3c5f21706">

**Step-8** Test lambda function -> check the result

<img width="696" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/2e820ad0-ede0-408b-be90-dfa6b083e63f">
<img width="696" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/e3eccc2d-0918-4499-90c7-dea99061b6c6">

# Nevigate to DynamoDB and IAM

<img width="565" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/8a5f29f0-0091-47c9-829d-3602476e8194">

**Step-1** create table -> insert name of table -> select ID -> then Click on Create table

<img width="833" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/02094cf4-7fa0-466f-9a2f-2582893e9451">
<img width="485" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/cc7b273b-e8f3-48ab-ac7a-7a3301133c2c">

**Step-2** click on mathfunction -> click on additional info-> copy that ARN -> paste in notepad

<img width="932" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/51709cbf-323a-4938-9718-e25c58c43e3b">
<img width="929" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/75d97da3-1f3e-4f4f-a635-a796fa2b7cac">

**Step-3** go to lambda function that we created in earlier steps -> go to Configuration -> clicl on permission -> click on power of math function-> open in new tab

<img width="571" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/d2ce199b-6d8c-470e-bbc8-23999efc55cb">
<img width="544" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/982b8f87-66ae-4cd9-9280-b2269036c524">
<img width="611" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/78fc9321-c8d9-4f94-89bb-ed55423ffd42">

**Step-4** click on json -> paste policy here 

<img width="510" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/e33c13f7-a9e3-4884-baf5-07b50a0b4cfa">

```
{
"Version": "2012-10-17",
"Statement": [
    {
        "Sid": "VisualEditor0",
        "Effect": "Allow",
        "Action": [
            "dynamodb:PutItem",
            "dynamodb:DeleteItem",
            "dynamodb:GetItem",
            "dynamodb:Scan",
            "dynamodb:Query",
            "dynamodb:UpdateItem"
        ],
        "Resource": "YOUR-TABLE-ARN"
    }
    ]
}

```

<img width="560" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/9714af2a-8b9d-46a6-b287-71615bcfad6f">

**Step-5** Paste your DyanamoDB ARN here -> click on review policy-> create policy

<img width="606" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/0a7164e1-6f7b-4806-9d3b-840c41832f1b">
<img width="618" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/274e4458-50c1-4846-aa52-5ffbd3ee3601">

**Step-6** Go to lambda function -> got to code-> paste code -> Test

<img width="539" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/3becb685-7978-46a2-b82e-ced8be3cbaec">

```
# import the JSON utility package
import json
# import the Python math library
import math

# import the AWS SDK (for Python the package name is boto3)
import boto3
# import two packages to help us with dates and date formatting
from time import gmtime, strftime

# create a DynamoDB object using the AWS SDK
dynamodb = boto3.resource('dynamodb')
# use the DynamoDB object to select our table
table = dynamodb.Table('PowerOfMathDatabase') # insert your name
# store the current time in a human readable format in a variable
now = strftime("%a, %d %b %Y %H:%M:%S +0000", gmtime())

# define the handler function that the Lambda service will use an entry point
def lambda_handler(event, context):

# extract the two numbers from the Lambda service's event object
    mathResult = math.pow(int(event['base']), int(event['exponent']))

# write result and time to the DynamoDB table using the object we instantiated and save response in a variable
    response = table.put_item(
        Item={
            'ID': str(mathResult),
            'LatestGreetingTime':now
            })

# return a properly formatted JSON object
    return {
    'statusCode': 200,
    'body': json.dumps('Your result is ' + str(mathResult))
    }

```
<img width="568" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/111b5dc2-089f-4b74-95cf-6007d7f1bd66">
<img width="599" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/c1874c18-4c9e-4b7e-9eb6-a37cd5024281">

**Step-7** go to dynamoDB -> Explore table item
<img width="656" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/9596b533-e923-4816-b968-df1ec5966aaa">

**we have the result you can check**

<img width="659" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/79954d93-3a03-44a9-8f15-0f8a5ddbef84">

**Step-8** Edit your index.html page again with following code -> add your api gate way link in code

```
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>To the Power of Math!</title>
    <!-- Styling for the client UI -->
    <style>
    h1 {
        color: #FFFFFF;
        font-family: system-ui;
		margin-left: 20px;
        }
	body {
        background-color: #222629;
        }
    label {
        color: #86C232;
        font-family: system-ui;
        font-size: 20px;
        margin-left: 20px;
		margin-top: 20px;
        }
     button {
        background-color: #86C232;
		border-color: #86C232;
		color: #FFFFFF;
        font-family: system-ui;
        font-size: 20px;
		font-weight: bold;
        margin-left: 30px;
		margin-top: 20px;
		width: 140px;
        }
	 input {
        color: #222629;
        font-family: system-ui;
        font-size: 20px;
        margin-left: 10px;
		margin-top: 20px;
		width: 100px;
        }
    </style>
    <script>
        // callAPI function that takes the base and exponent numbers as parameters
        var callAPI = (base,exponent)=>{
            // instantiate a headers object
            var myHeaders = new Headers();
            // add content type header to object
            myHeaders.append("Content-Type", "application/json");
            // using built in JSON utility package turn object to string and store in a variable
            var raw = JSON.stringify({"base":base,"exponent":exponent});
            // create a JSON object with parameters for API call and store in a variable
            var requestOptions = {
                method: 'POST',
                headers: myHeaders,
                body: raw,
                redirect: 'follow'
            };
            // make API call with parameters and use promises to get response
            fetch("YOUR API GATEWAY ENDPOINT", requestOptions) # add your api gate way link here
            .then(response => response.text())
            .then(result => alert(JSON.parse(result).body))
            .catch(error => console.log('error', error));
        }
    </script>
</head>
<body>
    <h1>TO THE POWER OF MATH!</h1>
	<form>
        <label>Base number:</label>
        <input type="text" id="base">
        <label>...to the power of:</label>
        <input type="text" id="exponent">
        <!-- set button onClick method to call function we defined passing input values as parameters -->
        <button type="button" onclick="callAPI(document.getElementById('base').value,document.getElementById('exponent').value)">CALCULATE</button>
    </form>
</body>
</html>

```

<img width="670" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/d9418f46-3327-4323-8263-bcf71dac0606">

**Step-9** zip that index.html file and open Amplify -> import in Amplify

<img width="676" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/a8dc856a-3138-4071-82f0-f633740711b2">

<img width="674" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/4884d418-9d0a-4f3b-8d84-6098a9a803cc">

**Step-10** Copy that Domain and paste in google -> add input -> click on Calculate -> see result

<img width="619" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/07a7e7b6-8ad1-4847-9db1-9d9258fed6a4">

<img width="508" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/bafe2442-578c-4296-8c51-deb02288d051">

<img width="583" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/42fceb1b-0380-4e5c-94f3-1f0378e85e5e">

**Last stage** :red_circle:  **Turn off Resource**

<img width="449" alt="image" src="https://github.com/SRUSHTI2493/AWS-Serverless-Web-Application/assets/87080882/cc56ec49-ae2a-4e8d-8ec4-2a50bd1073c9">


