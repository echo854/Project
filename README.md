# Project
Here is my python work code

def calculate_bmi(weight_kg, height_m):
    """
    Calculates the Body Mass Index (BMI) and determines the weight status.

    Args:
        weight_kg (float): Weight in kilograms.
        height_m (float): Height in meters.

    Returns:
        float: The calculated BMI value.
    """
    if height_m <= 0 or weight_kg <= 0:
        return "Invalid input: Weight and height must be positive values."

    # BMI Formula: weight (kg) / [height (m)]^2
    try:
        bmi = weight_kg / (height_m ** 2)
    except ZeroDivisionError:
        return "Invalid input: Height cannot be zero."

    # Determine the weight status category
    if bmi < 18.5:
        category = "Underweight"
    elif 18.5 <= bmi < 24.9:
        category = "Normal weight"
    elif 25.0 <= bmi < 29.9:
        category = "Overweight"
    else: # bmi >= 30.0
        category = "Obesity"

    print(f"\n--- BMI Result ---")
    print(f"Weight: {weight_kg:.2f} kg")
    print(f"Height: {height_m:.2f} m")
    print(f"Your BMI is: {bmi:.2f}")
    print(f"Category: **{category}**")
    print(f"------------------\n")

    return bmi

# --- Example Usage ---

# Example 1: A person weighing 70 kg and 1.75 meters tall
print("Example 1:")
calculate_bmi(weight_kg=70, height_m=1.75)

# Example 2: A person weighing 95 kg and 1.80 meters tall
print("Example 2:")
calculate_bmi(weight_kg=95, height_m=1.80)
