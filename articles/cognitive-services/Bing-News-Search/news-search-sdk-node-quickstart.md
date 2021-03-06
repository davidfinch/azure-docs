---
title: News Search SDK Node quickstart | Microsoft Docs
description: Set up the News Search SDK console application
titleSuffix: Azure cognitive services News search SDK Node quickstart
services: cognitive-services
author: mikedodaro
manager: rosh
ms.service: cognitive-services
ms.technology: bing-news-search
ms.topic: article
ms.date: 02/12/2018
ms.author: v-gedod
---

# News Search SDK Node quickstart

The Bing News Search SDK contains the functionality of the REST API for news queries and parsing results. 

## Application dependencies

To set up a console application using the Bing News Search SDK, run `npm install azure-cognitiveservices-newssearch` in your development environment.

## News Search client
Get a [Cognitive Services access key](https://azure.microsoft.com/try/cognitive-services/) under *Search*. Create an instance of the `CognitiveServicesCredentials`:
```
const CognitiveServicesCredentials = require('ms-rest-azure').CognitiveServicesCredentials;
let credentials = new CognitiveServicesCredentials('YOUR-ACCESS-KEY');
```
Then, instantiate the client:
```
const NewsSearchAPIClient = require('azure-cognitiveservices-newssearch');
let client = new NewsSearchAPIClient(credentials);
```
Use the client to search with a query text, in this case 'Winter Olympics':
```
client.newsOperations.search('Winter Olympics').then((result) => {
    console.log(result.value);
}).catch((err) => {
    throw err;
});
});

```
The code prints `result.value` items to the console without parsing any text.

![News results](media/node-sdk-quickstart-results.png)

## Next steps

[Cognitive services Node.js SDK samples](https://github.com/Azure-Samples/cognitive-services-node-sdk-samples)
