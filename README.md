# Rule-Based-Expert-System-using-Forward-Chaining-
Internship – Project 2.
Special thanks to @syntecxhub for providing this project opportunity.


---

⭐ Project Overview

This rule-based expert system:

Builds a small rule engine (if–then rules)

Accepts user facts (symptoms)

Infers conclusions using forward chaining

Supports multi-step inference

Logs reasoning steps so users can understand the reasoning path



---

🔧 Features

✔ Forward chaining inference
✔ Multiple rules and conditions
✔ Dynamic user input
✔ Clear reasoning trace
✔ Beginner-friendly AI project


---

📌 Technologies Used

Python 3

Rule-based AI concepts

Text-based interface



---

🧩 How Forward Chaining Works

1. User enters symptoms (facts).


2. The engine checks which rules match the facts.


3. When a rule matches, the THEN conclusion is inferred.


4. New conclusions may trigger more rules.


5. Final diagnosis is displayed



**EXAMPLE :-**
=== Rule-Based Expert System ===
Enter your symptoms (comma separated): fever, cough

Processing your symptoms...

✔ Matched Rule: ['fever', 'cough']
👉 Diagnosis: Flu


# -------------------------------------------
# Rule-Based Expert System (Forward Chaining)
# -------------------------------------------

rules = [
    {"if": ["fever", "cough"], "then": "Flu"},
    {"if": ["headache"], "then": "Migraine"},
    {"if": ["vomiting", "fever"], "then": "Food Poisoning"},
    {"if": ["sore throat"], "then": "Throat Infection"},
    {"if": ["fever", "rash"], "then": "Viral Infection"},
    {"if": ["fatigue", "body pain"], "then": "Dengue (Possible)"},
]

print("=== Rule-Based Expert System ===\n")
print("Example Symptoms: fever, cough, headache, vomiting, rash, fatigue\n")

user_input = input("Enter your symptoms (comma separated): ").lower()
symptoms = [s.strip() for s in user_input.split(",")]

print("\nProcessing your symptoms...\n")

matched = False

for rule in rules:
    if all(condition in symptoms for condition in rule["if"]):
        print("✔ Matched Rule:", rule["if"])
        print("👉 Diagnosis:", rule["then"])
        matched = True
        break

if not matched:
    print("❗ No matching diagnosis found for the given symptoms.")

print("\nThank you for using the Expert System!")
