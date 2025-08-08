# Converter
def celsius_to_fahrenheit(c):
    return (c * 9/5) + 32

def fahrenheit_to_celsius(f):
    return (f - 32) * 5/9

def kilometers_to_miles(km):
    return km * 0.621371

def miles_to_kilometers(mi):
    return mi / 0.621371

def kilograms_to_pounds(kg):
    return kg * 2.20462

def pounds_to_kilograms(lb):
    return lb / 2.20462

# Mapping option to (function, from_unit, to_unit)
conversion_map = {
    "1": (celsius_to_fahrenheit, "°C", "°F"),
    "2": (fahrenheit_to_celsius, "°F", "°C"),
    "3": (kilometers_to_miles, "km", "miles"),
    "4": (miles_to_kilometers, "miles", "km"),
    "5": (kilograms_to_pounds, "kg", "lbs"),
    "6": (pounds_to_kilograms, "lbs", "kg")
}

def main():
    while True:
        print("\n--- Unit Converter ---")
        print("1. Celsius to Fahrenheit")
        print("2. Fahrenheit to Celsius")
        print("3. Kilometers to Miles")
        print("4. Miles to Kilometers")
        print("5. Kilograms to Pounds")
        print("6. Pounds to Kilograms")
        print("7. Exit")

        choice = input("Select a conversion (1-7): ")

        if choice == "7":
            print("Goodbye!")
            break

        if choice in conversion_map:
            try:
                value = float(input(f"Enter value in {conversion_map[choice][1]}: "))
                func, from_unit, to_unit = conversion_map[choice]
                result = func(value)
                print(f"{value:.2f} {from_unit} = {result:.2f} {to_unit}")
            except ValueError:
                print("Invalid input. Please enter a numeric value.")
        else:
            print("Invalid choice. Please select a valid option.")

if __name__ == "__main__":
    main()
