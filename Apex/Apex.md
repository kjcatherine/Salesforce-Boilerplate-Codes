# Batch Apex
This is a snippet for making a batch class.


## BATCH APEX SNIPPET
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

## TEST CLASS
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
