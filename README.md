# Contact-book-using-Python
class ContactBook:
    def __init__(self):
        self.contacts = {}
        print("Welcome to the Contact Book!")
    def add_contact(self, name, phone, email):
        if not name or not phone:
            print("Error: Name and phone are required.")
            return
        self.contacts[name] = {'phone': phone, 'email': email}
        print(f"Contact '{name}' added successfully.")

    def search_contact(self, name):
        if name in self.contacts:
            contact = self.contacts[name]
            print(f"Name: {name}\nPhone: {contact['phone']}\nEmail: {contact['email']}")
        else:
            print(f"Contact '{name}' not found.")

    def delete_contact(self, name):
        if name in self.contacts:
            del self.contacts[name]
            print(f"Contact '{name}' deleted successfully.")
        else:
            print(f"Contact '{name}' not found.")

    def list_contacts(self):
        if not self.contacts:
            print("No contacts available.")
        else:
            print("All Contacts:")
            for name, details in self.contacts.items():
                print(f"- {name}: {details['phone']} ({details['email']})")


if __name__ == "__main__":
    book = ContactBook()
    book.add_contact("Charlie", "123-456-7890", "alice@example.com")
    book.add_contact("Bobby", "987-654-3210", "bob@example.com")
    book.list_contacts()
    book.search_contact("Charlie")
    book.delete_contact("Bobby")
    book.list_contacts()
