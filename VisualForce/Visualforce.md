# Visualforce
Boilerplate for Visualforce markup and controllers


## Visualforce Markup
```
<apex:page>
    //content that can go here - text, htmltags, VF tags, merge fields, ajax, css etc.
</apex:page>
```

## Visualforce controllers

### Standard controller
```
<apex:page standardController="standardsObject | customsObject__c">
//code goes here
</apex:page>
```

### Custom controller

#### Markup
```
<apex:page controller="controllerClassName" tabStyle="sObject">
//code goes here
</apex:page>
```

#### Apex code | use "with sharing" or "without sharing" in definition
```
public class controllerClassName {

    private final sObjectdataType variableName;

    public controllerClassName() { //use logic as needed
        variableName = [SELECT Id, field1, field2 FROM sObject
                       WHERE Id = :ApexPages.currentPage().getParameters().get('id')];
    }
    //get method
    public sObjectName getSobjectName() {
        return account;
    }
    //other code
    public PageReference save() {
        //handle exception here
        update sObject;
        return null;
        //navigate to the default view page after save
        PageReference redirectSuccess = new ApexPages.StandardController(sObject).view();
        return (redirectSuccess);
    }
    //other code
}

```

