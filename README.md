# Design Patterns and Principles with Example

### Design Principles
1. Program to Interface not Implementation
2. Favor Composition over Inheritance

### SOLID Design Principles
1. **S**ingle Responsibility : Class should have one and only one reason to change.
   Consider Payroll Application, In Employee class with
    1) calculatePay
    2) generateReport
    3) SaveOrUpdateEmployee methods
    break Single Responsibility principles, Employee class can modify or change by multiple Reason like change in Pay, Change       Report Generation view, Change in DB , so Instead of One Employee class we may have three class for individual                 responsibility like EmployeeWageCalculator, EmployeeReportGenerator and EmployeeDAO
    
    Same Principle also applied with method, Method should have one and only one reason to change.
    
2. **O**pen/Close Princile : Class should be open for extension, but close for modification.
3. **L**iskov Subsitution Principle : Let q(x) be a property provable about object x of type T. Then q(y) should be provable about object y of type S. where S is subtype of T.
  Subclass behave in a such way that it will not cause any problem when it use instead of SuperClass.
4. **I**nterface Segregation Principle : Client should not be forced to depend upon interface that they don't use.
5. **D**ependency Inversion Principle : High level module should not depend on low level module. Both should depend upon abstraction. Abstraction should not depend upon detail, Detail should depend upon abstraction.
  
