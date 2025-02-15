# Exam-Q2


### A)

In the code, inheritance is shown through the `BookstoreException` class, which acts as a parent for `OutOfStockError` and `PaymentProcessingError`. Since both subclasses extend `BookstoreException`, they can be handled as `BookstoreException` instances. This allows `PhysicalBookstore` to explicitly declare that it throws either `OutOfStockError` or `PaymentProcessingError`, while `OnlineBookstore` generalizes this by declaring throws `BookstoreException`, meaning it can throw any subclass of `BookstoreException`.

Polymorphism is used in the try-catch structure. Even though both specific exceptions (`OutOfStockError` and `PaymentProcessingError`) inherit from `BookstoreException`, Java determines at runtime which exact exception is thrown. In `OnlineBookstore`, the `processOrder()` method is declared to throw `BookstoreException`, but it actually throws either `OutOfStockError` or `PaymentProcessingError`. This is an example of polymorphism, where a general type (`BookstoreException`) is used in the method signature, but the actual exception object is one of its specific subclasses.
