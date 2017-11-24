# Design Patterns and Principles with Example

### Design Principles
1. Program to Interface not Implementation
2. Favor Composition over Inheritance

### SOLID Design Principles
1. **S**ingle Responsibility : **Class should have one and only one reason to change.**

   Consider Payroll Application, this application have class **Employee**  with
    1) **calculatePay**
    2) **generateReport**
    3) **SaveOrUpdateEmployee methods**
    
    break Single Responsibility principles, Employee class can modify or change by multiple Reason like change in Pay, Change     Report Generation view, Change in DB , so Instead of One Employee class we may have three class for individual               responsibility like EmployeeWageCalculator, EmployeeReportGenerator and EmployeeDAO
    
    Same Principle also applied with method, **Method should have one and only one reason to change.**
    
    Another Example: OTPHandler class with three method -> generateOTP, saveOTP, sendNotification
    
2. **O**pen/Close Princile : Class should be open for extension, but close for modification.
   
   For Example, we have application which integrate with Payment Gateway. Currently Application supports payment gateways
   like BillDesc, PayMoney, Citrus. Our class should be design like if new Payment gateway support require, we should not 
   change our class it easily extend with our application.
   
   For this we can use **Strategy** Pattern or Java Polimorphism.
   
   Another Example is **RestTemplate** of Spring support default HTTPMessageConverterts like json, xml, bytearray and others.
   Rest Template also extendable for support other converters like Google Protpbuff Http Converter.
   
3. **L**iskov Subsitution Principle :Derived classes must be substitutable for their base classes.
   
   Subclass behave in a such way that it will not cause any problem when it use instead of SuperClass.
   
   For example, Square is a Recatancle, But if extend Rectangle in Square class then Square has two method setWidth
   setHeight. Consider Scanrio, where one use Rectangle reference and Square Object, on invoking setWidth method Height 
   also be changed because of Square object. But invoker want to set only width of Rectangle. For resolve this kind of 
   issue we can caheck **instance of**  check using if condition which again break Open/Close Condition. So in above
   scanario, No Relation required between Square and Rectangle.
   
   Another example of Toy Duck should not derived from Duck, It look like Duck, Quack like Duck but requires battery.
   
   
4. **I**nterface Segregation Principle : Client should not be forced to depend upon interface that they don't use.
   
   The Interface Segregation Principle states that clients should not be forced to implement interfaces they don't use. 
   Instead of one fat interface, many small interfaces are preferred based on groups of methods, 
   each one serving one submodule.
   
   For Example, we have one Web Service interface which publish all web service for Provision,
   Login, Notification, Monitor, Audit web service. So if any channge occurs in Provision web service
   the the client which not use this web service also may changed. So Instead of one Fat interface we can
   create separate group interface of web service for Login, Provision, Notification. Monitor and Audit web
   service.
5. **D**ependency Inversion Principle : High level module should not depend on low level module. Both should depend upon  
   abstraction. Abstraction should not depend upon detail, Detail should depend upon abstraction.
   
   Generally, High Level modules deped upon low level module. For Example our code start with High level Controller to
   Service to DAO to JDBC Code(low level). Any changes in low level affect to High level. But If we created one 
   interface between High level and Low level then High level and low level both depend on abstration. So Any change
   to low level not affect to high level. Thats the reason it called Dependency Inversion Principle.

  
