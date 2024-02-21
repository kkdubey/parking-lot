```plaintext
+------------------+       +------------------+      +--------------+
|    ParkingLot    |-------|     GateEntry    |      |   Payment    |
+------------------+       +------------------+      +--------------+
| - parkingLot: Map<string, ParkingFloor>        |      |              |
| - paymentFactory: PaymentFactory               |      |              |
+------------------+       +------------------+      |              |
| + parkVehicle(vehicle: Vehicle): boolean       |      | + process(amount: int): boolean |
| + processPayment(amount: int): boolean         |      +--------------+
| + isFull(): boolean                            |
+-----------------------------------------------+

+------------------+       +--------------+
|   ParkingSpot    |       |   Vehicle    |
+------------------+       +--------------+
| - size: int      |       |              |
| - occupied: boolean     |       |              |
| - vehicle: Vehicle      |       |              |
+------------------+       +--------------+
| + isOccupied(): boolean |       |              |
| + occupy(vehicle: Vehicle): void           |
| + release(): void                            |
+-----------------------------------------------+

+------------------+       +---------------------+
|    ParkingFloor  |       |    PaymentFactory   |
+------------------+       +---------------------+
| - floorNumber: string      |       + choosePaymentMethod(): Payment   |
| - spots: List<ParkingSpot>                   |
+------------------+       +---------------------+

+------------------+       +------------------+
|    PaymentOption |       |    Vehicle       |
+------------------+       +------------------+
| - type: PaymentType     |       |              |
+------------------+       +------------------+
| + process(amount: int): boolean |       |              |
+------------------+       +------------------+

+------------------+       +------------------+
|   PaymentType    |       |  ParkingStrategy |
+------------------+       +------------------+
| CARD             |       |                  |
| CASH             |       + findBestSpot(): ParkingSpot |
+------------------+       +------------------+

+------------------+       +------------------+
|     Payment      |       |  Vehicle         |
+------------------+       +------------------+
| - amount: int    |       |                  |
+------------------+       +------------------+
| + processPayment(amount: int): boolean       |
+-----------------------------------------------+
