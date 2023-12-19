from abc import ABC, abstractmethod

# Абстрактні продукти
class Button(ABC):
    @abstractmethod
    def paint(self):
        pass

class Checkbox(ABC):
    @abstractmethod
    def render(self):
        pass

# Конкретні продукти для Windows
class WindowsButton(Button):
    def paint(self):
        print("Відображення кнопки для Windows")

class WindowsCheckbox(Checkbox):
    def render(self):
        print("Відображення прапорця для Windows")

# Конкретні продукти для Mac
class MacButton(Button):
    def paint(self):
        print("Відображення кнопки для Mac")

class MacCheckbox(Checkbox):
    def render(self):
        print("Відображення прапорця для Mac")

# Абстрактна фабрика
class GUIFactory(ABC):
    @abstractmethod
    def create_button(self) -> Button:
        pass

    @abstractmethod
    def create_checkbox(self) -> Checkbox:
        pass

# Конкретні фабрики для Windows та Mac
class WindowsFactory(GUIFactory):
    def create_button(self) -> Button:
        return WindowsButton()

    def create_checkbox(self) -> Checkbox:
        return WindowsCheckbox()

class MacFactory(GUIFactory):
    def create_button(self) -> Button:
        return MacButton()

    def create_checkbox(self) -> Checkbox:
        return MacCheckbox()

# Клієнтський код
class Client:
    def __init__(self, factory: GUIFactory):
        self.button = factory.create_button()
        self.checkbox = factory.create_checkbox()

    def render(self):
        self.button.paint()
        self.checkbox.render()

# Приклад використання
if __name__ == "__main__":
    # Для Windows
    windows_factory = WindowsFactory()
    windows_client = Client(windows_factory)
    windows_client.render()

    # Для Mac
    mac_factory = MacFactory()
    mac_client = Client(mac_factory)
    mac_client.render()
