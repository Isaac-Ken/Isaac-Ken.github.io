**Steganography with Digital Invisible Ink Toolkit (DIIRT)**
---
**Anlyzing photos for stegonogrpahy**  
I have modified the photo below using [Digital Invisible Ink Toolkit](http://diit.sourceforge.net/)  
![Barn_Owl](https://user-images.githubusercontent.com/66635295/160784188-55b0ffdf-e845-46dc-9c32-22e9bcaf155e.png)  

[source](https://www.owlpages.com/owls/authors.php?a=10)  

**What is Digital Invisible Ink Toolkit**  
"The Digital Invisible Ink Toolkit is a Java steganography tool that can hide any sort of file inside a digital image (regarding that the message will fit, and the image is 24 bit colour). It will work on Windows, Linux and Mac OS because it is written in Java and thus platform independent."  
![diirt1](https://user-images.githubusercontent.com/66635295/160772964-186e6240-759a-4d25-a9ba-d39bafe6e42e.png)  


**Running (DIIRT)**  
Using the decode tab were going to upload are image and check for any hidden messages  
![diirt2](https://user-images.githubusercontent.com/66635295/160773981-d495eacc-8f7d-4ea9-b0b4-94a203c70bf2.png)  

**Analyzing the photo**  
It appears the word salt is hidden in the wood  
![Barn_Owl_Salt](https://user-images.githubusercontent.com/66635295/160774572-ca90ba94-d984-40aa-9ee4-3c99ea31aaf4.png)  
lets try this in our password box  
![diirt3](https://user-images.githubusercontent.com/66635295/160774905-4f241d4b-e199-4da8-b21d-0c0f0ef896a4.png)  


**HideSeek**    
This algorithm randomly distributes the message across the image    
(you wouldnt necessarily know which algorithm)    
![diirt4](https://user-images.githubusercontent.com/66635295/160775691-2d6d2bd5-1e68-41aa-94f4-b901b6db241a.png)    

**Set Message**  
Save an empty txt file to your desktop to write to  
![diirt5](https://user-images.githubusercontent.com/66635295/160777368-13ca01b2-7b33-4945-9775-6f73d1dd8c7a.png)  

**Success**
Successfull retrieval 
![succ](https://user-images.githubusercontent.com/66635295/160778823-669c6050-606e-4bb9-bd4c-a55a85b1f4ee.png)  
 
 Reading the file we see it's mostly unreadable but  JFIF is of intrest  
 
![jfif](https://user-images.githubusercontent.com/66635295/160779136-b842d100-7e31-4dc3-8c1c-d37f3d59c52f.png)  

**TXT to JPG**  
Changing the .txt to a .jpg reveals a new image  
![convert](https://user-images.githubusercontent.com/66635295/160785193-50bad0f9-9737-46f0-af36-fcbba421f5d1.png)  

**New Image**  
The new image has some encrypted text on it   
![Barn-Owl-1-280di-280x420](https://user-images.githubusercontent.com/66635295/160784256-fd52c521-876f-49ff-b9a5-0c771476916b.jpg)  

[source](https://www.birdlife.org.au/bird-profile/barn-owl)

**Decrypt**  
The text appears to be in base64 encryption  
Using [base64decoder](https://www.base64decode.org/)  
<pre>TjFnaHQgMHdM</pre>  
We get the hidden message  
![decrypt](https://user-images.githubusercontent.com/66635295/160781392-f8be564d-646c-485c-8845-af3b8078acc4.png)




