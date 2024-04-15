# Backend Lecture - Testing

## Types Of Testing
1. Unit Testing
2. Integration Testing
3. Functional Testing

## Why testing?
``` java
int numberofLanes(int comesOnOneSide){
    return multiplyUtility(comesOnOneSide);
    
}

int multiplyUtility(int comesOnOneSide){
    return comesOnOneSide * 2;
}

int totalNumberOfShoes(int uniquePairs){
    return multiplyUtility(uniquePairs);
}
```
This function might be used at multiple other places and you cannot change this function as it might break other functionalities. So, you need to test this function to make sure it is working as expected.
If you don't test this function, you might end up breaking other functionalities.
You should have proper written test cases for every method written in your code.

If someday lanes coming on one side changes to 3, you need to change the multiplyUtitlity method to multiply by 3. If you don't have test cases, you might end up breaking other functionalities like counting totalNumberOfShoes.

### Test Case
``` java
testMultiplyUtility(){
    int x = multiplyUtility(10);
    if(x != 20){
        throw new Exception("Test failed");
    }
}
```
If this function gets triggered automatically whenever you deploy/push/run the code, if there is any error, it will get caught.
Sometimes in testing 2 out of 100 test case might fail, these cases are called corner cases or edge cases.
When the firms get big like google, amazon, facebook etc. people keep coming and leaving the company. So, if you don't have test cases, you might end up breaking other functionalities.

## SDLC - Software Development Life Cycle
The Software Development Life Cycle (SDLC) is a structured process used to design, develop, and test high-quality software. It’s a methodology that defines the entire procedure of software development step-by-step. The goal of SDLC is to deliver high-quality, maintainable software that meets the user’s requirements.

The SDLC involves six key stages:

1. **Planning and Requirement Analysis:** This is the most crucial stage where the basic project is designed with all the available information.
2. **Defining Requirements:** In this stage, all the requirements for the target software are specified.
3. **Designing Architecture:** The software architecture is designed in this stage.
4. **Developing Product:** The actual development of the software product takes place in this stage.
5. **Product Testing and Integration:** The developed product is tested and integrated in this stage.
6. **Deployment and Maintenance of Products:** Finally, the product is deployed and maintained.

As a software engineer it's equally important to write test cases for the feature we are implementing. It's a good practice to write test cases before writing the actual code.
Before we submit a feature it's important to run all the test cases and we will be able to submit the code if and only if all the test cases are passed.

## Test Driven Development (TDD)
* Test cases are written before writing the actual code.
* Initially all the test cases will fail.
* Write code, keep running the test cases against the code until all the test cases pass.
* Once all the test cases pass, submit the code.

## Flaky Test Cases
Flaky test cases are test cases that sometimes pass and sometimes fail. This is a big problem in the industry. If you have flaky test cases, you cannot trust the test cases. You need to make sure that all the test cases are passing before submitting the code.


## Unit Testing
* Ideally we should try to test functions in isolation. For example, if ```A``` is a function in which function ```B``` is written. If there is bug in function ```B``` then test case of function ```A``` should not fail. It should only fail when there is a bug in function ```A```.
* It says that test case of function ```A``` should only fail if there is some bug in function ```A```. It should not depend on any internal function. Every Individual unit of code should be tested.

## Integration Testing
* Testing each functionality of the application where all the dependencies also get called as they are written in real code. Therefore, no hard coding.
* In a function of product service, it will actually call the repository method.
* Relatively slower than unit testing.
* Fewer in number compared to unit test cases.
* It is important to test the integration of the code.
* We may mock external dependencies like database, network calls etc.

## Functional Testing
* No mocking at all
* End-to-End testing - testing the complete functionality of the application.