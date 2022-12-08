# Apex Unit Tests
Boilerplate for Apex Unit Tests.


## Apex Unit Tests - Method 1
```
@isTest
private class ClassNameTest {
	@isTest static void testMethodName(){
        //create an sobject for testing purposes
        <sOjbectName> variableName = new <sOjbectName>();
        variableName.field = value;
        insert variableName;    
    }
}
```

## Apex Unit Tests - Method 2
```
@isTest
private class ClassNameTest {
    @isTest static void testMethodName() {
        //instantiate class
        ClassName variableName = new ClassName(argument);
        //other processing here
        System.assertEquals(expected, actual);
    }
}
```

## Apex Unit Tests - Method 3
```
@isTest
private class ClassNameTest {
    @testSetup static void TestClass(){
    //Insert setup operations
    }
    @isTest static void testMethodName() {

        Test.startTest();
        //Asynchronous processing here
        Test.stopTest();
        
        //assert records were updated properly
        System.assertEquals(expected, actual);
    }
}
```



