```mermaid
class ParkingLot {
  - parkingLot: Map<string, ParkingFloor>
  - paymentFactory: PaymentFactory
  + parkVehicle(vehicle: Vehicle): boolean
  + processPayment(amount: int): boolean
  + isFull(): boolean
}

class GateEntry {
}

class Payment {
  - amount: int
  + process(amount: int): boolean
}

class ParkingSpot {
  - size: int
  - occupied: boolean
  - vehicle: Vehicle
  + isOccupied(): boolean
  + occupy(vehicle: Vehicle): void
  + release(): void
}

class ParkingFloor {
  - floorNumber: string
  - spots: List<ParkingSpot>
}

class PaymentFactory {
  + choosePaymentMethod(): Payment
}

class PaymentOption {
  - type: PaymentType
  + process(amount: int): boolean
}

class PaymentType {
}

class ParkingStrategy {
  + findBestSpot(): ParkingSpot
}

class Vehicle {
}

ParkingLot "1" -- "1" GateEntry
ParkingLot "1" -- "1" Payment
ParkingLot "1" -- "1" PaymentFactory
ParkingSpot "1" -- "1" Vehicle
ParkingFloor "1" -- "1" ParkingSpot
ParkingFloor "1" -- "1" PaymentFactory
Payment "1" -- "1" PaymentOption
PaymentOption "1" -- "1" PaymentType
ParkingStrategy "1" -- "1" ParkingSpot
```mermaid
