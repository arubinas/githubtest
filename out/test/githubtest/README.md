import tkinter as tk
from datetime import datetime

def calculate_age():
# Get user input (day, month, year)
day = int(day_entry.get())
month = int(month_entry.get())
year = int(year_entry.get())

    # Calculate age
    today = datetime.today()
    birth_date = datetime(year, month, day)
    
    if today.month < birth_date.month or (today.month == birth_date.month and today.day < birth_date.day):
        age = today.year - birth_date.year - 1
    else:
        age = today.year - birth_date.year
    
    # Display age
    age_label.config(text=f"Age: {age} years")

# Create the main window
window = tk.Tk()
window.title("Age Calculator")

# Labels and Entry Fields
day_label = tk.Label(window, text="Day: ")
day_entry = tk.Entry(window)

month_label = tk.Label(window, text="Month: ")
month_entry = tk.Entry(window)

year_label = tk.Label(window, text="Year: ")
year_entry = tk.Entry(window)

# Calculate button
calculate_button = tk.Button(window, text="Calculate Age", command=calculate_age)

# Age display label
age_label = tk.Label(window, text="Age")

# Grid layout
day_label.grid(row=0, column=0)
day_entry.grid(row=0, column=1)

month_label.grid(row=1, column=0)
month_entry.grid(row=1, column=1)

year_label.grid(row=2, column=0)
year_entry.grid(row=2, column=1)

calculate_button.grid(row=3, columnspan=2)

age_label.grid(row=4, columnspan=2)

# Start the GUI event loop
window.mainloop()
