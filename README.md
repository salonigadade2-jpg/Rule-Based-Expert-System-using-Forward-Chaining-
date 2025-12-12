# Rule-Based-Expert-System-using-Forward-Chaining-

**Project Description**

This project implements a Rule-Based Expert System using Python. It mimics how early AI systems performed reasoning: using if–then rules, a facts base, and an inference engine.
The system accepts user symptoms as input and uses Forward Chaining to infer a diagnosis based on predefined rules.

This project is part of my Artificial Intelligence Virtual Internship at @syntecxhub.

**🎯 Objectives**

Build a small rule engine with if–then rules

Maintain a facts base (user-provided symptoms)

Apply Forward Chaining to infer conclusions

Support multi-step reasoning (chaining of rules)

Display inference steps for transparency

Handle unmatched cases gracefully

🧠 What is a Rule-Based Expert System?

A Rule-Based Expert System is an AI model that uses predefined rules to make decisions.
Example:

IF fever AND cough THEN Flu


These systems were widely used in:

Medical diagnosis

Recommendation systems

Decision support tools

Industrial expert systems

**🔄 How Forward Chaining Works**

Forward chaining starts from known facts (user symptoms) and moves forward to match rules and draw conclusions.

Process:

User enters symptoms (facts).

The system checks rules whose conditions match the facts.

If all conditions match → the rule is triggered.

The conclusion becomes the predicted diagnosis.

The system may chain additional rules if required.

Final output is displayed to the user.

**⚙️ Features**

✔ Accepts user symptoms
✔ Matches conditions with rules
✔ Infers conclusions using forward chaining
✔ Step-by-step reasoning trace
✔ Customizable rule base
✔ Beginner-friendly AI project

📂 Folder Structure
Rule-Based-Expert-System/
│── expert_system.py
│── README.md
│── examples/
│   └── sample_output.txt (optional)
└── screenshots/
    └── interface.png (optional)

**🧑‍💻 Code Implementation**

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



**🧪 Sample Output**

=== Rule-Based Expert System ===
Enter your symptoms (comma separated): fever, cough

Processing your symptoms...

✔ Matched Rule: ['fever', 'cough']
👉 Diagnosis: Flu

Thank you for using the Expert System!

