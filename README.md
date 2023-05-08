# API
Backend API from a small e-com website(sample)
class Product:
    def __init__(self, name, barcode, brand, description, price, available):
        self.name = name
        self.barcode = barcode
        self.brand = brand
        self.description = description
        self.price = price
        self.available = available

class User:
    def __init__(self, first_name, last_name, email, password):
        self.first_name = first_name
        self.last_name = last_name
        self.email = email
        self.password = password

class Website:
    def __init__(self):
        self.users = []
        self.products = []

    def add_user(self, user):
        self.users.append(user)

    def get_user(self, email):
        for user in self.users:
            if user.email == email:
                return user
        return None

    def add_product(self, product):
        self.products.append(product)

    def get_product_by_barcode(self, barcode):
        for product in self.products:
            if product.barcode == barcode:
                return product
        return None

    def get_products(self):
        return self.products

    website = Website()

    product1 = Product('Product 1', '34567890', 'Brand 1', 'This is sample description', 200, True)
    website.add_product(product1)

    product2 = Product('Product 2', '4567890', 'Brand 2', 'This is sample description', 100, False)
    website.add_product(product2)

    product3 = Product('Product 3', '987654', 'Brand 3', 'This is sample description', 150, True)
    website.add_product(product3)


    products = website.get_products()
    for product in products:
        print(product.name, product.barcode, product.brand, product.desescription, product.price, product.available)
