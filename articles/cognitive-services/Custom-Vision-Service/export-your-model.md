---
title: Export your model to mobile  | Microsoft Docs
description: Export your model to mobile 
services: cognitive-services
author: anrothMSFT
manager: anroth

ms.service: cognitive-services
ms.technology: custom vision service
ms.topic: article
ms.date: 09/25/2017
ms.author: anroth
---
 
 

# Export your model to mobile 

Custom Vision Service allows classifiers to be exported to run offline. You can embed your exported classifier into an application and run it locally on a device for real-time classification. Currently the supported are export to Tensorflow for Android devices or the CoreML format for iOS11.

Custom Vision Service only exports “compact” domains. The models generated by compact domains are optimized for the constraints of real-time classification on mobile devices. Classifiers built with a compact domain may be slightly less accurate a standard domain with the same amount of training data. The tradeoff is that they are small enough to be run locally in near real time. For general tips on improving your classifiers, see [Getting Started: Improving your classifier.](https://docs.microsoft.com/azure/cognitive-services/custom-vision-service/getting-started-improving-your-classifier)

## Convert your project to a “compact” domain
If you are starting from scratch to build a new classifier, see [Getting Started: Build a Classifier](https://docs.microsoft.com/azure/cognitive-services/custom-vision-service/getting-started-build-a-classifier). However, when choosing a domain for your classifier, you must select a compact domain. 

 ![Select a compact domain.](./media/export-your-model/new-project-domain.png)
 
 If you have an existing classifier, you need to convert it to a compact domain. To convert the domain of an existing classifier:
1. Open the project you want to convert to a compact domain. You can find a list of your projects at [https://customvision.ai/projects](https://customvision.ai/projects). 
2. Open the settings page for this classifier by clicking on the gear-shaped icon at the top right. From within the setting page, select a **compact** domain and then hit **Save Changes.**
3. After changing your domain, you will need to hit the **Train** button to train your project.

 ![Change settings to a compact domain.](./media/export-your-model/change-project-domain.PNG)

## Export your model
Once your project has finished training, you can export your model. To do so:
1. Go to the **Performance** tab and select the iteration you want to export (probably your most recent iteration.)
3. If this iteration used a compact domain, an export button appears at the top bar. 
4. Click on **export**, then select your format.
5. Click on **export** and then **download** to download your model. 

 ![Export project.](./media/export-your-model/export-project.png)

## Next Steps
A sample of how to [use your exported CoreML model in an iOS application](https://go.microsoft.com/fwlink/?linkid=857726) for real-time image classification is available in Swift, as is an example iOS application for [using your exported CoreML model with Xamarin](https://github.com/xamarin/ios-samples/tree/master/ios11/CoreMLAzureModel). A sample of how to [use your exported Tensorflow model in an Android application](https://github.com/Azure-Samples/cognitive-services-android-customvision-sample) for real-time image classification is also available.
