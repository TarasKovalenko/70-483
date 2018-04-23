# Programming in C# (70-483)

Question 1
------
You are creating a class named Game.  
The Game class must meet the following requirements:  
1. Include a member that represents the score for a Game instance.  
2. Allow external code to assign a value to the score member.  
3. Restrict the range of values that can be assigned to the score member.  

You need to implement the score member to meet the requirements.  
In which form should you implement the score member?

**A**. protected field  
**B**. public static field  
**C**. public static property  
**D**. public property  

**_Answer: D_**
#
Question 2
------
An application includes a class named **Person**. The Person class includes a method named **GetData**.  
You need to ensure that the **GetData()** from the Person class.  
Which access modifier should you use for the **GetData()** method?

**A**. Internal  
**B**. Protected  
**C**. Private  
**D**. Protected internal  
**E**. Public  

**_Answer: B_**

_Explanation: Protected - The type or member can be accessed only by code in the same class or structure, or in a class that is derived from that class. http://msdn.microsoft.com/en-us/library/ms173121.aspx The protected keyword is a member access modifier. A protected member is accessible within its class and by derived class instances._
#
Question 3
------
You are developing a C# application that has a requirement to validate some string input
data by using the Regex class.  
The application includes a method named **ContainsHyperlink**.  The **ContainsHyperlink()**
method will verify the presence of a URI and surrounding markup.  
The following code segment defines the **ContainsHyperlink()** method. (Line numbers are
included for reference only.)

```csharp
01. bool ContainsHyperlink(string inputData) 
02. {
03.    string regExPattern = "href\\s*=\\s*(?:\"(?<1>[^\"]*)\"|(?<1>\\S+))";
04.
05.    return evaluator.IsMatch(inputData);
06. }
```

The expression patterns used for each validation function are constant.  
You need to ensure that the expression syntax is evaluated only once when the **Regex**
object is initially instantiated.  
Which code segment should you insert at line **04**?

**A**
```csharp
var evaluator = new Regex(regExPattern, RegexOptions.CultureInvariant);
```
**B** 
```csharp
var evaluator = new Regex(inputData);
```
**C**
```csharp
var assemblyName= "validation"; 
var compilationInvo = new RegexCompilationInfo(inputData, RegexOptions.IgnoreCase, "Href", assemblyName, true);
Regex.CompileToAssembly(new[] {compilationInfo}, new AssemblyName(assemblyName));
var evaluator = new Regex(regExPattern, RegexOptions.CultureInvariant);
```
**D**
```csharp
var evaluator = new Regex(regExPattern, RegexOptions.Compiled);
```

**_Answer: D_**

_Explanation: RegexOptions.Compiled - Specifies that the regular expression is compiled to an assembly.This yields faster execution but increases startup time.This value should not be assigned to the Options property when calling the CompileToAssembly method. http://msdn.microsoft.com/en-us/library/system.text.regularexpressions.regexoptions.aspx Additional info http://stackoverflow.com/questions/513412/how-does-regexoptions-compiled-work_
#
Question 4
------
You are developing an application.The application converts a Location object to a string by using a method named WriteObject.
The **WriteObject()** method accepts two parameters, a Location object and an
**XmlObjectSerializer** object.
The application includes the following code. (Line numbers are included for reference only.)

![alt text](https://raw.githubusercontent.com/TarasKovalenko/70-483/master/assets/q4.png)


You need to serialize the Location object as a JSON object.  
Which code segment should you insert at line 20?  

**A**. new XmlSerializer(typeof(Location))  
**B**. new NetDataContractSerializer()  
**C**. new DataContractJsonSerializer(typeof (Location))  
**D**. new DataContractSerializer(typeof(Location))  

**_Answer: D_**

_Explanation: The code is using [DataContract] attribute here so need to used DataContractSerializer class._
