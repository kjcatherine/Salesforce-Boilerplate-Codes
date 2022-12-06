# Apex Trigger
Boilerplate for Apex Trigger


## Apex Trigger
```
trigger TriggerName on ObjectName (trigger_events) {
    //Bulkify
    List<sObjectName> variableNameBulk = List<sObjectName>(); 

    //Trigger loop
    for (<sObjectName> variableName : Trigger.new) { 
        variableName.fieldName = value;
        //other processing
        variableNameBulk.add(variableName);
    }
    
    DMLStatement variableNameBulk;
    }
```



