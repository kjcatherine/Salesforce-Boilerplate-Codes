# Apex Class
Boilerplate for Apex class.


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



