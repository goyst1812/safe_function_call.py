import colorama

def call_function_safely(module, function_name):
    try:
        # Отримуємо функцію
        func = getattr(module, function_name)
        if callable(func):
            print(f"Викликаємо функцію '{function_name}':")
            func()  
        else:
            print(f"'{function_name}' існує, але не є функцією.")
    except AttributeError:
        print(f"Функція '{function_name}' не знайдена в модулі {module.__name__}.")


call_function_safely(colorama, "init")


call_function_safely(colorama, "non_existing_function")
