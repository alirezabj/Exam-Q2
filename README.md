# Exam-Q2


### A)

In the code, inheritance is shown through the `BookstoreException` class, which acts as a parent for `OutOfStockError` and `PaymentProcessingError`. Since both subclasses extend `BookstoreException`, they can be handled as `BookstoreException` instances. This allows `PhysicalBookstore` to explicitly declare that it throws either `OutOfStockError` or `PaymentProcessingError`, while `OnlineBookstore` generalizes this by declaring throws `BookstoreException`, meaning it can throw any subclass of `BookstoreException`.

Polymorphism is used in the try-catch structure. Even though both specific exceptions (`OutOfStockError` and `PaymentProcessingError`) inherit from `BookstoreException`, Java determines at runtime which exact exception is thrown. In `OnlineBookstore`, the `processOrder()` method is declared to throw `BookstoreException`, but it actually throws either `OutOfStockError` or `PaymentProcessingError`. This is an example of polymorphism, where a general type (`BookstoreException`) is used in the method signature, but the actual exception object is one of its specific subclasses.


### B)

The code does not work because the `BookPriceCalculator` class returns an Object from `calculatePrice` but `DiscountedBookPriceCalculator` overrides it with a return type of Double. In Java, when overriding a method, the return type must be the same or a subclass of the original return type. Since Double is not a direct subclass of Object, the method override is invalid. To fix this, both methods should return Double instead of Object.

##### Advantages and Disadvantages:
1. One benifit of the code is that the `BookPriceCalculator` class keeps all pricing rules in one place, making it easy to update or modify (Encapsulation). It also allows subclasses like `DiscountedBookPriceCalculator` to modify pricing rules, such as adding discounts. However, the major drawback is that the subclass changes the return type from Object to Double, which is not allowed in Java and causes a compilation error.
