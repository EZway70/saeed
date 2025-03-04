class Customer:
    """Represents a customer in the delivery system."""

    def __init__(self, customerID, name, email, password, address):
        """Initializes the customer with their details."""
        self.__customerID = customerID  # Private attribute for customer ID
        self.__name = name  # Private attribute for customer name
        self.__email = email  # Private attribute for customer email
        self.__password = password  # Private attribute for password
        self.__address = address  # Private attribute for customer address

    # Getters - Methods to access private attributes
    def getCustomerID(self):
        return self.__customerID

    def getName(self):
        return self.__name

    def getEmail(self):
        return self.__email

    def getPassword(self):
        return self.__password

    def getAddress(self):
        return self.__address

    # Setters - Methods to modify private attributes
    def setCustomerID(self, customerID):
        self.__customerID = customerID

    def setName(self, name):
        self.__name = name

    def setEmail(self, email):
        self.__email = email

    def setPassword(self, password):
        self.__password = password

    def setAddress(self, address):
        self.__address = address

    # Functional Methods
    def login(self):
        """Handles user login verification (to be implemented)."""
        pass  # Placeholder for future login implementation

    def placeOrder(self):
        """Processes customer order placement (to be implemented)."""
        pass

    def trackOrder(self):
        """Tracks customer order status (to be implemented)."""
        pass

    def displayCustomerDetails(self):
        """Returns customer details including Customer ID as a formatted string."""
        return f"Customer ID: {self.__customerID}\nCustomer Name: {self.__name}\nEmail: {self.__email}\nAddress: {self.__address}\n"


class Order:
    """Represents an order placed by a customer."""

    def __init__(self, orderID, customerID, items, status="Pending"):
        """Initializes the order with default status as 'Pending'."""
        self.__orderID = orderID
        self.__customerID = customerID
        self.__items = items  # List of items in the order
        self.__status = status  # Order status (Pending, Shipped, etc.)

    # Getters
    def getOrderID(self):
        return self.__orderID

    def getCustomerID(self):
        return self.__customerID

    def getStatus(self):
        return self.__status

    def getItems(self):
        return self.__items

    # Setters
    def setOrderID(self, orderID):
        self.__orderID = orderID

    def setCustomerID(self, customerID):
        self.__customerID = customerID

    def setStatus(self, status):
        self.__status = status

    def setItems(self, items):
        self.__items = items

    def verifyAvailability(self):
        """Verifies if ordered items are in stock (to be implemented)."""
        pass

    def confirmOrder(self):
        """Confirms order processing (to be implemented)."""
        pass

    def displayOrderDetails(self):
        """Returns order details as a formatted string."""
        order_details = f"Order ID: {self.__orderID}\nOrder Status: {self.__status}\nItems Ordered:\n"
        for item in self.__items:  # Loop through items in the order
            order_details += f"  - {item}\n"
        return order_details


class Admin:
    """Represents an administrator managing orders and deliveries."""

    def __init__(self, adminID, name, email, phoneNumber):
        """Initializes admin details."""
        self.__adminID = adminID
        self.__name = name
        self.__email = email
        self.__phoneNumber = phoneNumber

        # Getters

    def getAdminID(self):
        return self.__adminID

    def getName(self):
        return self.__name

    def getEmail(self):
        return self.__email

    def getPhoneNumber(self):
        return self.__phoneNumber

    # Setters
    def setAdminID(self, adminID):
        self.__adminID = adminID

    def setName(self, name):
        self.__name = name

    def setEmail(self, email):
        self.__email = email

    def setPhoneNumber(self, phoneNumber):
        self.__phoneNumber = phoneNumber

    def manageOrders(self):
        """Handles order management (to be implemented)."""
        pass

    def assignDelivery(self):
        """Assigns delivery tasks (to be implemented)."""
        pass

    def displayAdminDetails(self):
        """Returns admin details including Admin ID as a formatted string."""
        return f"Admin ID: {self.__adminID}\nAdmin Name: {self.__name}\nEmail: {self.__email}\nPhone: {self.__phoneNumber}\n"


class DeliveryStaff:
    """Represents a delivery staff handling deliveries."""

    def __init__(self, staffID, name, phoneNumber, assignedOrders):
        """Initializes delivery staff details."""
        self.__staffID = staffID
        self.__name = name
        self.__phoneNumber = phoneNumber
        self.__assignedOrders = assignedOrders

        # Getters

    def getStaffID(self):
        return self.__staffID

    def getName(self):
        return self.__name

    def getPhoneNumber(self):
        return self.__phoneNumber

    def getAssignedOrders(self):
        return self.__assignedOrders

    # Setters
    def setStaffID(self, staffID):
        self.__staffID = staffID

    def setName(self, name):
        self.__name = name

    def setPhoneNumber(self, phoneNumber):
        self.__phoneNumber = phoneNumber

    def setAssignedOrders(self, assignedOrders):
        self.__assignedOrders = assignedOrders

    def pickUpPackage(self):
        """Handles package pickup (to be implemented)."""
        pass

    def updateStatus(self):
        """Updates delivery status (to be implemented)."""
        pass

    def displayDeliveryDetails(self):
        """Returns delivery staff details including Staff ID as a formatted string."""
        return f"Staff ID: {self.__staffID}\nDelivery Staff: {self.__name}\nPhone: {self.__phoneNumber}\nAssigned Orders: {self.__assignedOrders}\n"


class Item:
    """Represents an item available for ordering."""

    def __init__(self, itemID, name, price, stock):
        """Initializes item details."""
        self.__itemID = itemID
        self.__name = name
        self.__price = price
        self.__stock = stock

    def getItemID(self):
        return self.__itemID

    def getName(self):
        return self.__name

    def getPrice(self):
        return f"{self.__price} AED"

    def getStock(self):
        return self.__stock

    def setItemID(self, itemID):
        self.__itemID = itemID

    def setName(self, name):
        self.__name = name

    def setPrice(self, price):
        self.__price = price

    def setStock(self, stock):
        self.__stock = stock

    def updateStock(self):
        pass

    def displayItemDetails(self):
        # """Returns item details including the item ID as a formatted string."""
        return f"Item ID: {self.__itemID}\nItem Name: {self.__name}\nPrice: {self.__price} AED\nStock: {self.__stock}\n"


# Creating Two Objects for Each Class
customer1 = Customer(1, "Zayed", "zayed@zu.ac.ae", "password123", "Abu Dhabi, UAE")
customer2 = Customer(2, "Ahmed", "ahmed@zu.ac.ae", "pass456", "Dubai, UAE")

order1 = Order(101, customer1.getCustomerID(), ["Laptop", "Mouse"], "Pending")
order2 = Order(102, customer2.getCustomerID(), ["Keyboard", "Monitor"], "Shipped")

admin1 = Admin(5001, "Prof. Afshan", "afshan@zu.ac.ae", "+971-50-1234567")
admin2 = Admin(5002, "Dr. Khalid", "khalid@zu.ac.ae", "+971-55-9876543")

staff1 = DeliveryStaff(7001, "Mohammed", "+971-52-6543210", [order1.getOrderID()])
staff2 = DeliveryStaff(7002, "Saeed", "+971-56-7890123", [order2.getOrderID()])

item1 = Item(1001, "GeForce RTX 4090", 3700, 5)
item2 = Item(1002, "Gaming Laptop", 8000, 2)

# Delivery Note for Customer1
print("\n" + "=" * 70)  # (\n) is only a line breaker, the statement should print "=" 70 times.
print(f"DELIVERY NOTE - Customer 1")
print("=" * 70)
print(customer1.displayCustomerDetails())  # Using display function for customer
print("-" * 50)
print(order1.displayOrderDetails())  # Using display function for order
print(item1.displayItemDetails())  # Using display function for item
print("-" * 50)
print(staff1.displayDeliveryDetails())  # Using display function for staff
print(admin1.displayAdminDetails())  # Using display function for admin
print("=" * 70)

# Delivery Note for Customer2
print("\n" + "=" * 70)
print(f"DELIVERY NOTE - Customer 2")
print("=" * 70)
print(customer2.displayCustomerDetails())  # Using display function for customer
print("-" * 50)
print(order2.displayOrderDetails())  # Using display function for order
print(item2.displayItemDetails())  # Using display function for item
print("-" * 50)
print(staff2.displayDeliveryDetails())  # Using display function for staff
print(admin2.displayAdminDetails())  # Using display function for admin
print("=" * 70)
