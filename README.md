def purchase(*items):
    products = {}
    for item in items:
        if len(item) != 2:
            raise ValueError("Каждый товар должен быть представлен в виде кортежа (название, цена).")
        name, price = item
        if not isinstance(name, str) or not isinstance(price, (int, float)):
            raise TypeError("Название товара должно быть строкой, а цена - числом.")
        products[name] = price
    return products

# Пример использования функции
try:
    items = (("Кружка", 300), ("Стакан", 400), ("кофе 500 гр", 800))
    result = purchase(*items)
    print(result)
except (ValueError, TypeError) as e:
    print(f"Ошибка: {str(e)}")
