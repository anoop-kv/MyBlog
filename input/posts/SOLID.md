Title: SOLID design principles
Published: 05/09/2022
Tags:
  - SOLID
  - C#
----
1. Single responsibility

    A module should have one and only one reason to change 

2. Open closed

    A module should be closed for modification but open for extension 

3. Liskov substitution

    It should be possible to substitute a base class with a subclass without breaking the application. 
    - There should be covariance of return types
    - Parameters should be contravariant
    - No new exceptions should be raised in the sub class 

    ```C#
    class BaseClass
    {
    }

    class SubClass : BaseClass
    {
    }


    class Program 
    {
        delegate BaseClass Covariance(SubClass subClass);
        delegate BaseClass ContraVariance(SubClass subClass);

        static SubClass MethodA(SubClass subClass)
        {
          Console.WriteLine("Method A");
          return new SubClass();
        }

        static BaseClass MethodB(SubClass subClass)
        {
          Console.WriteLine("Method B");
          return new BaseClass();
        }

        static void main()
        {
          Covariance covarianceExample = MethodA;
          ContraVariance contraVarianceExample = MethodB; 

          var baseClass1 = MethodA(new SubClass()); //

          var baseClass2 = MethodA(new BaseClass()); // Contravariance allows base class to be passed instead of sub class

        }

    }

    

    ```

4. Interface seggregation

    Clients should not be forced to depend upon an interface that they do not use

5. Dependency inversion

    High level module should not depend on low level modules. Both should use abstrations