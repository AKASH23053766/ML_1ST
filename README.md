[student_dataset.py](https://github.com/user-attachments/files/23816131/student_dataset.py)
# Simple student dataset

import pandas as pd
import os

# Create folder to save CSV safely
save_folder = "C:/Temp"  # Change this folder if you want
if not os.path.exists(save_folder):
    os.makedirs(save_folder)

# Create lists for 20 students
ID = list(range(1, 21))
Name = ["Student" + str(i) for i in range(1, 21)]
Age = [16] * 20
Subject = ["Math"] * 20
Score = [80] * 20

# Make the dataset
data = {
    "ID": ID,
    "Name": Name,
    "Age": Age,
    "Subject": Subject,
    "Score": Score
}

students = pd.DataFrame(data)

# Print the table
print(students)

# Save CSV safely in a folder where Python has permission
file_path = os.path.join(save_folder, "students.csv")
students.to_csv(file_path, index=False)
print(f"\nCSV file saved at: {file_path}")
