# SoapUI-API-project about testing a calculator

## Introduction
This project is about using SoapUI to test a calculator API. One test suit together with one test case was created. Test steps are including setting test step properties, creating Add step, Property Transfer and the final step called Multiply, wihch would use the result from Add step.  

## Project structure

![Project stucture](/images/SOAPUItestStructure.png "Structure pic")

Test suite called TestSuite 1.   
Test case name is End to end test.  
Four test steps:    
  1. testStepProperty: varible a = 23, and b =23. They are both test step level property
     
     ![test property](/images/testStepProperty.png "Property pic")
     
  3. Add: this step including five assertions inside. The request is using step level property, by ${testStepProperty#a} and ${testStepProperty#b}.
     For the five assertions, they can be told by their names for their purpose of expectation.
     
     ![Add step](/images/Add.png "Add pic")
     
  5. Property Transfer(add to multiply): it is used to get the result of response from Add step, and used later for Multiply step for request. Name space is required to get result as well as apply corresponding location in the Target step

     ![Property transfer](/images/PropertyTransfer.png "Property transfer pic")
     
  7. Muliply step is the final test step, which will use the reslut from previous step

      ![Multiply](/images/Multiply.png "Multiply pic")


    

