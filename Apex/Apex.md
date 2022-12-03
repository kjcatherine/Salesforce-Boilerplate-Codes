# Apex Class
This is a snippet for making an Apex class.


## Apex Class
```
//Class Definition, choose between private, public etc.
private | public | global class ClassName {
    
    //Class Variables
    private static final dataType variableName; 
    private final dataType variableName;

    // Constructor with no argument 
    public ClassName() {
            this(variableName);
    }
    // Constructor with one or more arguments 
    public ClassName(dataType argumentName) {
    this.variableName = argumentName;  | variableName = argumentName;
    }
    
    //Method with return | input parameters optional
    public | private | protected | global static dataType methodName() { 
        return; 
        //Logic here
     }
    //Method with no return 
    public static void methodName() { 
        //method logic here
     }
 }
```



# Batch Apex
This is a snippet for making a batch class.


## Batch Apex
```
public class ClassName implements Database.Batchable<sObject> {
    public (Database.QueryLocator | Iterable<sObject>) start(Database.BatchableContext bc) {
        //Choose between Database.QueryLocator or List<sObject> Query
        // collect the batches of records or objects to be passed to execute
    }
    public void execute(Database.BatchableContext bc, List<P> records){
        // process each batch of records
    }
    public void finish(Database.BatchableContext bc){
        // post-processing operations
}
}
```

## Test Class
```
@isTest
private class ClassNameTest {
    @testSetup static void TestClass(){
    //Insert setup operations
    }
    @isTest static void testMethodName() {
        
        Test.startTest();
        ClassName batchTester = new ClassName();
        Id batchId = Database.executeBatch(batchTester);
        Test.stopTest();

        //assert records were updated properly
        System.assertEquals(expected, actual, 'message');
    }
}
```
