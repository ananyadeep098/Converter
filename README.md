def celsius_to_fahrenheit(c):
    return (c * 9/5) + 32

def fahrenheit_to_celsius(f):
    return (f - 32) * 5/9

def kilometers_to_miles(km):
    return km * 0.621371

def miles_to_kilometers(miles):
    return miles / 0.621371

def kilograms_to_pounds(kg):
    return kg * 2.20462

def pounds_to_kilograms(lb):
    return lb / 2.20462

conversions = {
    "1": ("Celsius to Fahrenheit", celsius_to_fahrenheit, "°C", "°F"),
    "2": ("Fahrenheit to Celsius", fahrenheit_to_celsius, "°F", "°C"),
    "3": ("Kilometers to Miles", kilometers_to_miles, "km", "miles"),
    "4": ("Miles to Kilometers", miles_to_kilometers, "miles", "km"),
    "5": ("Kilograms to Pounds", kilograms_to_pounds, "kg", "lbs"),
    "6": ("Pounds to Kilograms", pounds_to_kilograms, "lbs", "kg")
}

def unit_converter():
    while True:
        print("\n--- Unit Converter ---")
        for key, value in conversions.items():
            print(f"{key}. {value[0]}")
        print("7. Exit")
        
        choice = input("Choose a conversion: ")
        
        if choice == "7":
            print("Exiting Unit Converter. Goodbye!")
            break
        elif choice in conversions:
            try:
                value = float(input(f"Enter value in {conversions[choice][2]}: "))
                result = conversions[choice][1](value)
                print(f"{value:.2f} {conversions[choice][2]} = {result:.2f} {conversions[choice][3]}")
            except ValueError:
                print("Invalid input! Please enter a numeric value.")
        else:
            print("Invalid choice! Please select a valid option.")

if __name__ == "__main__":
    unit_converter()
