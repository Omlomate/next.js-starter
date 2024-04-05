<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Toingg API Documentation</title>
  <style>
    body {
      margin: 0; 
    }

    header {
      background-color: #f8f9fa; /* Light gray background */
      padding: 20px;
    }

    .sidebar {
      position: fixed;
      top: 150px; /* Adjust the top position to avoid overlapping with header */
      left: 0;
      width: 250px;
      height: calc(100% - 70px); /* Subtract header height from total height */
      background-color: #0000; /* Light gray background */
      overflow-y: auto;
      padding: 20px;
       /* Add a border to separate from content */
    }

    .sidebar h2 {
      margin-top: 0;
      margin-bottom: 20px; /* Add some space below heading */
      color: #ffff; /* Dark text color */
      font-size: 18px; /* Larger font size for headings */
    }

    .endpoint-link {
      display: block;
      margin-bottom: 10px;
      text-decoration: none;
      color: #3B2F6; /* Medium gray text color */
      font-size: 16px; /* Medium font size */
      transition: color 0.3s; /* Smooth color transition on hover */
    }

    .endpoint-link:hover {
      color: #ffff;
    }

    main {
      margin-left: 270px; /* Adjust margin-left to match sidebar width */
      padding: 20px;
    }
    
  </style>
</head>
<body>

<header>
  <h1>Toingg API Documentation</h1>
  <p>Welcome to the Toingg API documentation. This document provides detailed information about the Toingg API endpoints, parameters, request bodies, and responses.</p>
</header>

<div class="sidebar">
  <h2>Endpoints</h2>
  <ul>
    <li><a class="endpoint-link" href="#make-toingg">Make Toingg</a></li>
    <li><a class="endpoint-link" href="#make-toingg-details">Make Toingg Details</a></li>   
    <li><a class="endpoint-link" href="#make-batch-toingg">Make Batch Toingg</a></li>
    <li><a class="endpoint-link" href="#send-sms">Send SMS</a></li>
    <li><a class="endpoint-link" href="#hang-up-call">Hang Up Call</a></li>
    <li><a class="endpoint-link" href="#create-checkout-session">Create Checkout Session</a></li>
     <li><a class="endpoint-link" href="#stripe-webhook">Stripe Webhook</a></li>
    <!-- Add more endpoint links as needed -->
  </ul>
  <h2>Schemas</h2>
  <ul>
    <li><a class="endpoint-link" href="#api-key">APIKEY</a></li>
    <li><a class="endpoint-link" href="#api-key">HTTPValidationError</a></li>
    <li><a class="endpoint-link" href="#api-key">ValidationError</a></li>
    <li><a class="endpoint-link" href="#api-key">makeBatchCallData</a></li>
    <li><a class="endpoint-link" href="#api-key">makeCallData</a></li>
    <li><a class="endpoint-link" href="#api-key">makeCallDetailsData</a></li>
    <li><a class="endpoint-link" href="#api-key">AnumberDataPIKEY</a></li>
    <li><a class="endpoint-link" href="#api-key">smsData</a></li>

</div>

<main>
  
  <h1 id="make-toingg">Make Toingg</h1>
 

  ### <a name="make-toingg"></a>POST /make_toingg/ - Make Toingg

  #### Description
  Make Toingg.

  #### Parameters
  - **apiKey** (*required*): API key for authentication. Type: string. (Located in query)

  #### Request Body
  - **Content Type**: [`application/json`](#media-type)

  - **Example Value**:

  ```json
  {
    "campaign": "string",
    "name": "string",
    "phoneNumber": "string"
  }
  ```
  ## Responses

### 200 - Successful Response

-**Media type**: [`application/json`](#media-type)

- **Controls Accept header**
- **Example Value Schema**: `"string"`

### 422 - Validation Error

- **Media type**: [`application/json`](#media-type)

- **Example Value Schema**:
```json
{
  "detail": [
    {
      "loc": [
        "string",
        0
      ],
      "msg": "string",
      "type": "string"
    }
  ]
} 
```    
  <h1 id="make-toingg-details">Make Toingg Details</h1>

## POST /make_toingg_details/
### Make Toingg

### Parameters

#### Try it out

- **Name**: apiKey
  - *Description*: string (query)
  - *apiKey*

#### Request body

- **Content Type**: [`application/json`](#media-type)

- **Example Value**:

```json
{
  "campaignName": "string",
  "campaignScript": "string",
  "name": "string",
  "phoneNumber": "string"
}

```

## Responses

### 200 - Successful Response

- **Media type**: [`application/json`](#media-type)
- **Controls Accept header**
- **Example Value Schema**: "string"
- No links

### 422 - Validation Error

- **Media type**: application/json
- **Example Value Schema**:

```json
{
  "detail": [
    {
      "loc": [
        "string",
        0
      ],
      "msg": "string",
      "type": "string"
    }
  ]
}
``` 

  <h1 id="make-batch-toingg">Make Batch Toingg</h1>

  ## POST /make_batch_toingg/

Make Toingg

### Parameters

- **apiKey**: *string* (query) - API key for authentication

#### Request body

- **Content Type**: [`application/json`](#media-type)

- **Example Value**:

```json
{
  "campaign": "string",
  "numberList": [
    {
      "clientName": "string",
      "clientNumber": "string"
    }
  ]
}
```
## Responses

#### 200 - Successful Response

- **Media type**:  [`application/json`](#media-type)
- Controls Accept header.
- **Example Value Schema**: `"string"`
- No links

#### 422 - Validation Error

- **Media type**: [`application/json`](#media-type)
- **Example Value Schema**:

```json
{
  "detail": [
    {
      "loc": [
        "string",
        0
      ],
      "msg": "string",
      "type": "string"
    }
  ]
}
```

  <h1 id="send-sms">Send SMS</h1>

  ## POST /send_sms/
Send Sms

### Parameters
- **apiKey** (*required*): string (query)

### Request body
- **Content Type**:  [`application/json`](#media-type)
- **Example Value**:
```json
{
  "name": "string",
  "phoneNumber": "string",
  "message": "string"
}
```
## Responses

### 200 - Successful Response
- **Media type**:  [`application/json`](#media-type)
- **Controls Accept header**
- **Example Value Schema**: "string"
- No links

### 422 - Validation Error
- **Media type**:  [`application/json`](#media-type)
- **Example Value Schema**:
```json
{
  "detail": [
    {
      "loc": [
        "string",
        0
      ],
      "msg": "string",
      "type": "string"
    }
  ]
}
```

  <h1 id="hang-up-call">Hang Up Call</h1>
   
   ## POST /hang_up_call/

### Hang Up Call

#### Parameters

##### Try it out
- **callSid**: (*required*) string (query)
- **apiKey**: (*required*) string (query)
## Responses

### 200 - Successful Response

- **Media type**:  [`application/json`](#media-type)
- **Controls Accept header**
- **Example Value Schema**: `"string"`
- No links

### 422 - Validation Error

- **Media type**:  [`application/json`](#media-type)
- **Example Value Schema**:
```json
{
  "detail": [
    {
      "loc": [
        "string",
        0
      ],
      "msg": "string",
      "type": "string"
    }
  ]
}
```

  <h1 id="create-checkout-session">Create Checkout Session</h1>

  ## POST /create-checkout-session
Create Checkout Session

### Request Body

- **Media type**:  [`application/json`](#media-type)
- **Example Value Schema**:
```json
{
  "apikey": "string"
}
```
## Responses

### 200 - Successful Response

- **Media type**:  [`application/json`](#media-type)
- **Controls Accept header**
- **Example Value Schema**: `"string"`
- No links

### 422 - Validation Error

- **Media type**:  [`application/json`](#media-type)
- **Example Value Schema**:
```json
{
  "detail": [
    {
      "loc": [
        "string",
        0
      ],
      "msg": "string",
      "type": "string"
    }
  ]
}
```

  <h1 id="stripe-webhook">Stripe Webhook</h1>

  ## POST /webhook
Stripe Webhook

### Parameters
- Try it out: No parameters

## Responses

### 200 - Successful Response

- **Media type**:  [`application/json`](#media-type)
- **Controls Accept header**
- **Example Value Schema**: `"string"`
 

 <h1 id="api-key">Schemas</h1>
  

 ### APIKey

- **apikey**: string

### HTTPValidationError

- **detail**: array<object>

### ValidationError

- **loc**: array<(string | integer)>
- **msg**: string
- **type**: string

### makeBatchCallData

- **campaign**: string
- **numberList**: array<object>

### makeCallData

- **campaign**: string
- **name**: string
- **phoneNumber**: string

### makeCallDetailsData

- **campaignName**: string
- **campaignScript**: string
- **name**: string
- **phoneNumber**: string

### numberData

- **clientName**: string
- **clientNumber**: string

### smsData

- **name**: string
- **phoneNumber**: string
- **message**: string

  
  
 
</main>

<script>
  // Function to handle smooth scrolling to sections
  function scrollToSection(event) {
    event.preventDefault(); // Prevent default link behavior
    const targetId = event.target.getAttribute('href').substring(1); // Get the target section id
    const targetSection = document.getElementById(targetId); // Find the target section
    if (targetSection) {
      targetSection.scrollIntoView({ behavior: 'smooth' }); // Scroll to the target section smoothly
    }
  }

  // Add event listeners to all endpoint links
  const endpointLinks = document.querySelectorAll('.endpoint-link');
  endpointLinks.forEach(link => {
    link.addEventListener('click', scrollToSection);
  });
</script>

</body>
</html>

