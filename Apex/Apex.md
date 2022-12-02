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

## Test Class
```
@isTest
public class ClassNameTest {
    @testSetup static void TestClass(){
    //Insert operations
    }

    static testmethod void testMethodName() {

        Test.startTest();
        ClassName batchTester = new ClassName();
        ID BatchID = Database.executeBatch(batchTester);
        Test.stopTest();

        System.assertEquals(expected, actual, 'message');
    }

}
```
