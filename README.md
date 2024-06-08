class PhoneBook:
    def __init__(self):
        self.entries = {}

    def add_entry(self, name, phone_number):
        self.entries[name] = phone_number

    def get_entry(self, name):
        return self.entries.get(name, "Запись не найдена.")

    def update_entry(self, name, new_phone_number):
        if name in self.entries:
            self.entries[name] = new_phone_number
            return "Запись обновлена."
        else:
            return "Запись не найдена."

    def delete_entry(self, name):
        if name in self.entries:
            del self.entries[name]
            return "Запись удалена."
        else:
            return "Запись не найдена."

    def search(self, query):
        results = {name: num for name, num in self.entries.items() if query.lower() in name.lower()}
        return results if results else "Совпадений не найдено."

# Пример использования
phone_book = PhoneBook()
phone_book.add_entry("Иван Иванов", "123456789")
phone_book.add_entry("Петр Петров", "987654321")

# Изменение номера
print(phone_book.update_entry("Иван Иванов", "111222333"))

# Удаление записи
print(phone_book.delete_entry("Петр Петров"))

# Поиск по имени или фамилии
print(phone_book.search("Иван"))

