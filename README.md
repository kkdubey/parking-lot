```plantuml
@startuml
class Person {
  + name: String
  + age: Int
  + address: String
}

class Employee extends Person {
  + salary: Double
  + department: String
}

class Customer extends Person {
  + creditScore: Int
  + purchaseHistory: List<Purchase>
}

Person "1" --> "0..*" Employee
Person "1" --> "0..*" Customer
@enduml
