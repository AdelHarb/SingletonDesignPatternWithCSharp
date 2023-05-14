# SingletonDesignPatternWithCSharp
Simple Console app written with C#

This Summary is done by watching Passionate Coders Tutorial : https://www.youtube.com/watch?v=MfA48pQsXsg&list=PLsV97AQt78NTrqUAZM562JbR3ljX19JFR&index=2

Singleton Design Pattern is Creational Design Pattern meant for ensuring that there is only one instance
of the class across the application.(instructor only called once)

Use Case: where there are static Data or static resources that will not change often or it is acceptable to restart 
the application to refresh it. for example the application configuration.

How to apply singleton design pattern:

# 1- Making the Constructor Private, in my cae, in the EmployeeDataStore.

# 2- Making new _instance of the same type of the constructor.

#    notice that this reference "_instance" does not point to an object which will cause NullReferenceException
#    there is a solution which is eager initialization
#        private static EmployeeDataStore _instance = new();
#        this is a good easy solution in case of single application however in bigger application it will cause Race Condition Problem
#
#    the more handy solution is the Lazy Initialization
#        Which is to check in the Instance get property if the _instance equals null, in addition to that, before the if condition
#        we add lock to prevent the race condition.
#
#    to ensure more that there is no race condition
#    we can add another if condition for null checking before the lock that contains the if null checking.
