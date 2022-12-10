# Scheduled Apex
This is a snippet for making a scheduled class and test class.

## Scheduled Class

```
global class ClassName implements Schedulable {
    global void execute(SchedulableContext SC) {
      // code here
    }
}
```

## Test Class

```
@isTest
public class ClassNameTest {
    public static String CRON_EXP = '0 0 0 25 11 ? 2022'; //choose when to run | Seconds Minutes Hours Day_of_month Month Day_of_week optional_year | Midnight, 25 November

    static testmethod void testerMethod(){

        Test.startTest();
        String jobId = System.schedule('ScheduledApexTest', CRON_EXP, new SomeClass()); //create the scheduler instance
        Test.stopTest(); //Scheduler runs immediately after stopTest()

        System.assertEquals(expected, actual, 'message');
    }
}

```