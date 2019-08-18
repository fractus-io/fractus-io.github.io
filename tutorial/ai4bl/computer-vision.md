---
layout: tutorialpage
title: Computer Vision
permalink: /tutorials/ai4bl/computer-vision
path: /tutorials/ai4bl/
repo: https://github.com/fractus-io/ai4bl
tags: computer vision 
---

* [Introduction](#Introduction)

* [What is Computer Vision?](#WhatIsComputerVision)
* [Overview of Computer Vision](#OverviewOfComputerVision)
* [Data, data, data](#DataDataData)
* [Use cases for Computer Vision](#UseCasesForComputerVision)
* [Healthcare](#Healthcare)
* [Transportation](#Transportation)
* [Retail](#Retail)
* [Agriculture](#Agriculture)
* [FinancialServices](#FinancialServices)
* [Summary](#Summary)

###  <a id="Introduction"></a>Introduction

Artificial Intelligence (AI) is revolutionising every day life and causing a positive disruption in several industries. 
There are many applications of AI such as natural language processing (NLP) and machine learning (ML) but one of the key ones that 
perhaps hasn’t had as much exposure as though although is equally as ground-breaking is known as computer vision. 
Sticking with the abbreviations, computer vision is often referred to as CV. 

###  <a id="WhatIsComputerVision"></a>What is Computer Vision?

CV is defined as a field of study that looks to develop techniques that allows computers to see and understand the content of digital images like 
photographs or videos. CV goes beyond just putting a camera on your computer or laptop. The objective is to help machines view the world like 
people or animals do which is no small feat. Whilst that camera attached to your laptop might by able to see things, CV ensures they can also 
understand them. One example that we’ve all known for years is the ability to turn black lines into information about a product, commonly known 
as a barcode.

Computer vision is like the part of the human brain that processes what an image means with the camera being the part that sees the image, 
like our eyes.

###  <a id="OverviewOfComputerVision"></a>Overview of Computer Vision

Many popular computer vision applications involve trying to recognize things in photographs; for example:

•	Object Classification: What broad category of object is in this photograph?

	o	Grouping items into different categories like animals, people or buildings could be a basic example of this.

•	Object Identification: Which type of a given object is in this photograph?

	o	If we know the image is classified as an animal, is it a dog or a cat?

•	Object Verification: Is the object in the photograph?

	o	Is the object we know as a dog or a cat in the image being presented?

•	Object Detection: Where are the objects in the photograph?

	o	Also known as “edge detection”, this works out the outer edge of a landscape to better identify what is in the image

•	Object Landmark Detection: What are the key points for the object in the photograph?

	o	Could be checking whether there are key patterns to recognising the object within the image? Shapes, colours and visual indicators.

•	Object Segmentation: What pixels belong to the object in the image?

	o	Pieces of the image can be examined separately for a more accurate analysis

•	Object Recognition: What objects are in this photograph and where are they? 

	o	Not only detecting that an image is there but specifically identifying what it is.

Applications of computer vision will often only need to incorporate one of these techniques. However, more advanced cases such as driverless cars 
rely on several different methods to accomplish their goals. 

Whilst to a human, these tasks might not sound hugely complicated, machines struggle when an image is in a state that they might not expect. 
One of the best examples of CV in practice is the app, “Not Hotdog.” The concept of the app itself is incredibly unimpressive but when you consider 
the neural networks (an advanced type of AI) that happen behind the scenes, suddenly it falls nothing short of amazing. 

The app itself simply determines whether an image is a hotdog or not. It sounds ridiculous as nine times out of ten, a small child could recognise 
whether an object is a hotdog. However, what about when that hotdog is in difference states? For example, in a bun or out of a bun, at different 
angles, in a jar or replaced with a banana. The machine needs to be smart enough to recognise whether the item they are looking for is still present. 
Not Hotdog is amazingly accurate to a point where it can even tell the difference between a hotdog and a bratwurst. That is where machines have 
become impressive with image recognition. 

Typically, this type of image recognition operates via processes that take all the individual pixels of an image. A machine is trained with 
millions of images that humans will pre-label and help them recognise if future images are hotdogs or not. For example, the AI will create a 
view of what should be included within an image of a hotdog and make the appropriate decision having compared every pixel. Upon meeting a minimum 
threshold, the machine declares the result.

Not Hotdog is a trivial example, but CV is making important inroads into many industries where it is having a big impact. 

###  <a id="DataDataData"></a>Data, data, data

Although we tend to focus on the end user technology and results of any such system, the truth is that they are only effective if they have quality 
data feeding them. Beyond CV, this goes for virtually any application that operates using AI. 

Think about a machine that needed to determine whether an image was of a cat or a dog. The best way to approach computer vision is in the same way 
that you would approach a jigsaw puzzle. You start with all the pieces and the task is to assemble them in such a way that makes sense. 
The machine isn’t just given a final image and left to work it out but instead is fed hundreds, thousands or millions of items (data points/pixels) 
to train it to recognise what the objects might be. 

So, to find a cat, we wouldn’t just be telling a computer to search for whiskers and pointy ears. Millions of photos defining a cat or dog would be 
uploaded for the model to learn on its own the types of features that make each of them up. 

###  <a id="UseCasesForComputerVision"></a>Use cases for Computer Vision

We know what computer vision does and some of the different types but the key to any application of artificial intelligence comes with ensuring 
we can put it into practice.  Here are some case studies reviewing how computer vision is changing the face of different industries. 

###  <a id="Healthcare"></a>Healthcare

Using computer vision in healthcare is simultaneously one of the most ground-breaking and the most controversial developments in the 
industry (we’ll come on to this shortly). Using machine vision, AI vendors are able to create applications that diagnose patients as well as 
assisting with tasks like surgery, clinical trials and diagnostics. 

#### Diagnostics

Computer vision software is being used to help find abnormalities in patient scan images that may lead to an accurate diagnosis. 
For example, the US and Israeli-based company, MaxQ AI have developed a software that allows physicians to identify anomalies in patient brain scans. 
The professionals can then focus on the best course of treatment for the patients rather than spending a long time diagnosing them. 
 
One of the controversies, or at least talking points here, is that patients are wary that a machine is wary of their fate. 
For example, what would happen if the computer vision technology gets something wrong? Who is responsible? How can a machine be reprimanded? 
All of these are fair questions and one reason why such computer vision is yet to come into mainstream practice. 
In fact, companies like MaxQ AI specifically say their software is designed to accompany human knowledge and in no way replace it. 

All that said, the potential benefits outweigh the questions hanging over computer vision. Tests in Hong Kong have shown it to be more 
accurate than humans when diagnosing some forms of cancer. If these diagnostics can happen instantly, in the event of something like a stroke, 
the chances of a full recovery are drastically improved. 

#### Medical Imaging

Computer vision software like Arterys has been developed which can create 3D models of a patient’s heart on a radiologist’s computer screen. 
The software can reduce the time a radiologist needs to spend scanning patients and just like the applications used in diagnostics, allows them to 
focus their efforts of effective patient treatments. A comprehensive evaluation of the heart can be completed in 10 minutes and requires no 
technical training. 

This is achieved through training the software using millions of images of the heart and its surrounding areas. 

#### Clinical Trials

The New York based start-up, AiCure, have developed an app which monitors patients as they undergo clinical trials in an attempt to reduce the 
number of people who drop out. Using facial recognition technology, the app determines whether a patient has ingested a prescribed drug through 
the camera of their smartphone. Hours of footage collecting data would have been used to train the models and make sure the app is efficient. 

#### Surgery

The Triton software developed by Gauss is able to calculate surgical blood loss using computer vision. Surgeons can hold their surgical sponge to a 
screen and Triton works out the current blood loss rate. As with the other applications discussed, this would have required millions of training 
images to be accurate, depicting all kinds of different states for the sponge. 

In trials, Triton has been more accurate in determining the loss of blood during a C section than human counterparts. 
Those whose surgeries involved Triton experienced a shorter stay in hospital. 

###  <a id="Transportation"></a>Transportation

Most of us will be aware of the promise of driverless or autonomous vehicles. Innovations in computer vision are brining that sci-fi fantasy much 
closer to reality. 

To be autonomous, cars need a lot of input devices like cameras, radars and lasers so as they can attempt to perceive the world around them. 
For example, they will need to classify objects to identify whether they are a car, person, sign or something else. They will then need to detect 
where the object is, segment it and finally recognise it. In theory, driverless cars need to apply all the different types of computer vision 
techniques we talked about at the start of this article.  

Autonomous vehicles can only become mainstream once vehicles can do this highly effectively. One error in their perception could cause an accident 
which is why we haven’t seen them fully commercialised just yet.

With more than one million people killed in car accidents every year, detecting objects and safe driving has the potential to save a lot of 
lives whereby many incidents are caused by human error. For example, if the camera notices a cyclist raise their arm, computer vision will 
ascertain if there is a genuine signal of intent and create an action accordingly e.g. to slow down. 

###  <a id="Retail"></a>Retail

Amazon have trialled using computer vision to have fully automated stores that don’t require staff. The Amazon Go stores have facial recognition 
cameras at the entrance and tracks each person as they go through the store. It recognises if that person removes something from a shelf or 
puts it back on and adds it to their virtual basket accordingly. 

Once the shopper has finished in the store they simply walk out and are charged directly from their Amazon account for anything within their 
virtual basket. Trials of the store have been successful but there are a few flaws around “fuzziness” which is when the view of recognition 
software is blocked in some way. 

Once the minor glitches have been fixed, we could easily begin to see a host of computer vision operated stores popping up globally. 

###  <a id="Agriculture"></a>Agriculture

We don’t always think about agriculture as an industry that is ripe for disruption. However, it is one of those that has been employing computer 
vision technology to optimise operational efficiency to good effect. 

One of the most common applications is the use of drones. Traditionally, a farmer might have to manually review their crops and determine any 
threats to the yield. In using drones, they are able to do this by taking pictures of their crop and using those to scan for issues like 
infestation or slow growth. 

Computer vision models are loaded with millions of images showing what good and bad growth look like so it can classify multiple states. 
The data is filtered into analytics systems that provides insights allowing farmers to take actions and save their crops. 

###  <a id="FinancialServices"></a>Financial Services


Banks are increasingly turning to computer vision technology to remove the risk of fraudulent activity. This includes using fingerprint or retina scans as a method for customers to login to their accounts which are becoming commonplace in applications. 
As well as this, customers needing to deposit a cheque have the option to scan it and sending it to the bank where it gets authorised by their software. 

###  <a id="Summary"></a>Summary


Some industries are certainly ahead of other when it comes to computer vision technology, but we are starting to see a greater adoption across the board as companies begin to realise the ground-breaking potential. 
Right now, as the public still comes to terms with trusting machines over human interpretation, computer vision technology still requires supervision. There are no major use cases where it can completely replace human resource. For example, whilst some cars are driverless, they still have a human at the wheel supervising what happens. 
In the future, as we tweak and research computer vision, it is possible that some applications can completely eradicate the need for human input. 

