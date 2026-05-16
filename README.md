# SoapUI-API-project about testing a calculator

## Introduction
This project is about using SoapUI to test a calculator API. One test suit together with one test case was created. Test steps are including setting test step properties, creating Add step, Property Transfer and the final step called Multiply, wihch would use the result from Add step.  

## Project structure
Test suite called TestSuite 1.   
Test case name is End to end test.  
Four test steps:    
  1. testStepProperty: varible a = 23, and b =23. They are both test step level property
     
     ![test property](/images/testStepProperty.png "Property pic")
     
  3. Add: this step including five assertions inside. The request is using step level property, by ${testStepProperty#a} and ${testStepProperty#b}.
     For the five assertions, they can be told by their names for their purpose of expectation.
     
     ![Add step](/images/Add.png "Add pic")
     
  5. Property Transfer(add to multiply): it is used to get the result of response from Add step, and used later for Multiply step for request

     ![Property transfer](/images/PropertyTransfer.png "Property transfer pic")
     
  7. Muliply step is the final test step, which will use the reslut from previous step

>> testing

![Project stucture](/images/SOAPUItestStructure.png "Structure pic")

    
## Using **Runner** to automate this collection

The photo is a screenshot that shows this collection result. And there is one fialed API request due to repetitive registration of client.

<img width="1234" height="823" alt="image" src="https://github.com/user-attachments/assets/9672aa1c-4d28-48e8-947a-aac42819288f" />

## Other feature of this API testing 

The base API address and book ID has been stored in the varible.
