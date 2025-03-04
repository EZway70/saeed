class Customer:
    def __init__(self, customerID, name, email, password, address):
        self.__customerID = customerID
        self.__name = name
        self.__email = email
        self.__password = password
        self.__address = address

    def getCustomerID(self): return self.__customerID
    def getName(self): return self.__name
    def getEmail(self): return self.__email
    def getPassword(self): return self.__password
    def getAddress(self): return self.__address

    def setCustomerID(self, customerID): self.__customerID = customerID
    def setName(self, name): self.__name = name
    def setEmail(self, email): self.__email = email
    def setPassword(self, password): self.__password = password
    def setAddress(self, address): self.__address = address

    def displayCustomerDetails(self):
        return f"Customer ID: {self.__customerID}\nName: {self.__name}\nEmail: {self.__email}\nAddress: {self.__address}\n"

class Order:
    def __init__(self, orderID, customerID, items, status="Pending"):
        self.__orderID = orderID
        self.__customerID = customerID
        self.__items = items
        self.__status = status

    def getOrderID(self): return self.__orderID
    def getCustomerID(self): return self.__customerID
    def getStatus(self): return self.__status
    def getItems(self): return self.__items

    def setOrderID(self, orderID): self.__orderID = orderID
    def setCustomerID(self, customerID): self.__customerID = customerID
    def setStatus(self, status): self.__status = status
    def setItems(self, items): self.__items = items

    def displayOrderDetails(self):
        order_details = f"Order ID: {self.__orderID}\nStatus: {self.__status}\nItems:\n"
        for item in self.__items: order_details += f"  - {item}\n"
        return order_details

class Admin:
    def __init__(self, adminID, name, email, phoneNumber):
        self.__adminID = adminID
        self.__name = name
        self.__email = email
        self.__phoneNumber = phoneNumber

    def getAdminID(self): return self.__adminID
    def getName(self): return self.__name
    def getEmail(self): return self.__email
    def getPhoneNumber(self): return self.__phoneNumber

    def setAdminID(self, adminID): self.__adminID = adminID
    def setName(self, name): self.__name = name
    def setEmail(self, email): self.__email = email
    def setPhoneNumber(self, phoneNumber): self.__phoneNumber = phoneNumber

    def displayAdminDetails(self):
        return f"Admin ID: {self.__adminID}\nName: {self.__name}\nEmail: {self.__email}\nPhone: {self.__phoneNumber}\n"

class DeliveryStaff:
    def __init__(self, staffID, name, phoneNumber, assignedOrders):
        self.__staffID = staffID
        self.__name = name
        self.__phoneNumber = phoneNumber
        self.__assignedOrders = assignedOrders

    def getStaffID(self): return self.__staffID
    def getName(self): return self.__name
    def getPhoneNumber(self): return self.__phoneNumber
    def getAssignedOrders(self): return self.__assignedOrders

    def setStaffID(self, staffID): self.__staffID = staffID
    def setName(self, name): self.__name = name
    def setPhoneNumber(self, phoneNumber): self.__phoneNumber = phoneNumber
    def setAssignedOrders(self, assignedOrders): self.__assignedOrders = assignedOrders

    def displayDeliveryDetails(self):
        return f"Staff ID: {self.__staffID}\nName: {self.__name}\nPhone: {self.__phoneNumber}\nAssigned Orders: {self.__assignedOrders}\n"

class Item:
    def __init__(self, itemID, name, price, stock):
        self.__itemID = itemID
        self.__name = name
        self.__price = price
        self.__stock = stock

    def getItemID(self): return self.__itemID
    def getName(self): return self.__name
    def getPrice(self): return f"{self.__price} AED"
    def getStock(self): return self.__stock

    def setItemID(self, itemID): self.__itemID = itemID
    def setName(self, name): self.__name = name
    def setPrice(self, price): self.__price = price
    def setStock(self, stock): self.__stock = stock

    def displayItemDetails(self):
        return f"Item ID: {self.__itemID}\nName: {self.__name}\nPrice: {self.__price} AED\nStock: {self.__stock}\n"

# Creating Objects
customer1 = Customer(1, "Alice Brown", "alice.b@example.com", "alice123", "789 Oak St, Village")
customer2 = Customer(2, "Bob Green", "bob.g@example.com", "bob456", "321 Pine St, Hamlet")

order1 = Order(101, customer1.getCustomerID(), ["Headphones", "Adapter"], "Pending")
order2 = Order(102, customer2.getCustomerID(), ["Smartwatch", "Strap"], "Shipped")

admin1 = Admin(5001, "Admin Chris", "chris.admin@example.com", "+111-222-3333")
admin2 = Admin(5002, "Admin Taylor", "taylor.admin@example.com", "+444-555-6666")

staff1 = DeliveryStaff(7001, "Dave Wilson", "+777-888-9999", [order1.getOrderID()])
staff2 = DeliveryStaff(7002, "Eva Martinez", "+000-111-2222", [order2.getOrderID()])

item1 = Item(1001, "Wireless Headphones", 150, 20)
item2 = Item(1002, "Smartwatch Ultra", 300, 15)

# Delivery Note for Customer1
print("\n" + "=" * 50)
print("DELIVERY NOTE - Customer 1")
print("=" * 50)
print(customer1.displayCustomerDetails())
print(order1.displayOrderDetails())
print(item1.displayItemDetails())
print(staff1.displayDeliveryDetails())
print(admin1.displayAdminDetails())
print("=" * 50)

# Delivery Note for Customer2
print("\n" + "=" * 50)
print("DELIVERY NOTE - Customer 2")
print("=" * 50)
print(customer2.displayCustomerDetails())
print(order2.displayOrderDetails())
print(item2.displayItemDetails())
print(staff2.displayDeliveryDetails())
print(admin2.displayAdminDetails())
print("=" * 50)
