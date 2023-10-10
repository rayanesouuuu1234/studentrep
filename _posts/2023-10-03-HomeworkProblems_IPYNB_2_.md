---
toc: True
comments: False
layout: post
title: Homework problems Data Abstractions
type: hacks
courses: {'csp': {'week': 7}}
---

### Problem 1
- Two airplanes are in a race, your job is to make a plane name list, append the name value to the participents  then make a variable that pulls the distance covered for each plane. in the end, in the curly brackets print the name of the plane, add more variables with curly brackets. 


```python
# Define a list of airplane race participants
participants = [
    {"name": "Billium Bang", "plane": "Red Rocket", "distance_covered": 1200},
    {"name": "Bushawn Bal", "plane": "The Biggest Bird", "distance_covered": 1500}
]

# Calculate the total distance covered by each pilot during the race
for participant in participants:
    # Retrieve the details for each participant
    pilot_name = participant["name"]
    plane_name = participant["plane"]
    distance = participant["distance_covered"]
    
    # Print the details
    print(f"{pilot_name} in the '{plane_name}' covered a distance of {distance} miles!")

# Determine the winner
winner = max(participants, key=lambda x: x["distance_covered"])
print(f"The winner of the airplane race is {winner['name']} in the '{winner['plane']}' with a distance of {winner['distance_covered']} miles!")

```

    Billium Bang in the 'Red Rocket' covered a distance of 1200 miles!
    Bushawn Bal in the 'The Biggest Bird' covered a distance of 1500 miles!
    The winner of the airplane race is Bushawn Bal in the 'The Biggest Bird' with a distance of 1500 miles!


### Problem 2
- Add more participants , in the loop, add a tricks variable that gets data from participants list
    score = tricks * 10  # Each trick is worth 10 points
    add a score and add it to a score in the list ex list[score] = score


```python
# Define a list of dog show participants
participants = [
    {"name": "Fido", "breed": "Golden Retriever", "tricks": 4},
    # Add more dog participants as desired
]

# Calculate the scores for each dog based on the number of tricks they can perform
for participant in participants:
    tricks = participant["tricks"]
    score = tricks * 10  # Each trick is worth 10 points
    participant["score"] = score

# Determine the winning dog
winner = max(participants, key=lambda x: x["score"])

# Display the dog show results
print("Dog Show Results:")
for participant in participants:
    print(f"{participant['name']} the {participant['breed']} scored {participant['score']} points!")

print(f"The winner of the dog show is {winner['name']} with {winner['score']} points!")

```

    Dog Show Results:
    Fido the Golden Retriever scored 40 points!
    The winner of the dog show is Fido with 40 points!


this problem, were making a bank account, you just have to know what to do to add all of the functions to change the variables


```python
# Define a class representing a Bank Account
class BankAccount:
    def __init__(self, account_holder, balance=0):
        self.account_holder = account_holder
        self.balance = balance

    def deposit(self, amount):
        if amount > 0:
            self.balance += amount
            print(f"Deposited ${amount}. New balance: ${self.balance}")
        else:
            print("Invalid deposit amount.")

    def withdraw(self, amount):
        if 0 < amount <= self.balance:
            self.balance -= amount
            print(f"Withdrew ${amount}. New balance: ${self.balance}")
        else:
            print(f"Insufficient funds to withdraw ${amount}. Current balance: ${self.balance}")
                
    def get_balance(self):
        return f"Balance for {self.account_holder}: ${self.balance}"

    def __str__(self):
        return f"{self.account_holder}'s Account with balance: ${self.balance}"


# Create two bank accounts Alex with 1000$ initially, and Noah with 5$ initially:
alexAccount = BankAccount("Alex", 1000)
noahAccount = BankAccount("Noah", 5)

# Perform some transactions: withdraw all money from Alex and give it to Noah
alex_withdrawal = alexAccount.balance
alexAccount.withdraw(alex_withdrawal)
noahAccount.deposit(alex_withdrawal)

# Noah goes on a spending spree and withdraws all of his money
noah_withdrawal = noahAccount.balance
noahAccount.withdraw(noah_withdrawal)

# Display account information
print("Alex Account:", alexAccount)
print("Noah Account:", noahAccount)

```

    Withdrew $1000. New balance: $0
    Deposited $1000. New balance: $1005
    Withdrew $1005. New balance: $0
    Alex Account: Alex's Account with balance: $0
    Noah Account: Noah's Account with balance: $0


### add more regions



```python
import random

# Define a list of regions, each represented as a dictionary
regions = [
    {
        "name": "Region A",
        "GDP_growth": random.uniform(0.5, 3.0),  # Random GDP growth rate between 0.5% and 3.0%
        "unemployment_rate": random.uniform(3.0, 10.0),  # Random unemployment rate between 3.0% and 10.0%
        "investment_score": random.uniform(50, 100),  # Random investment score between 50 and 100
        "education_index": random.uniform(0.5, 1.0),  # Random education index between 0.5 and 1.0
        "infrastructure_quality": random.uniform(3.0, 8.0)  # Random infrastructure quality between 3.0 and 8.0 (scale of 1-10)

    },
    {
        "name": "region B",
        "GDP_growth": random.uniform(1.0,3.0),
        "unemployment_rate": random.uniform(4.0, 6.0),
        "investment_score": random.uniform(66, 89),
        "education_index": random.uniform(0.75, 0.99),
        "infrastructure_quality": random.uniform(3.2, 7.8)
    }
    # Define more regions
]

# Define weights for each economic indicator
weights = {
    "GDP_growth": 0.4,
    "unemployment_rate": -0.2,
    "investment_score": 0.3,
    "education_index": 0.1,
    "infrastructure_quality": 0.2
}

# Function to calculate a score for each region based on economic indicators and weights
def calculate_score(region):
    score = 0
    for indicator, weight in weights.items():
        score += region[indicator] * weight
    return score

# Find the region with the highest economic growth potential
best_region = max(regions, key=calculate_score)

# Display information about the winning region
print(f"The region with the highest economic growth potential is {best_region['name']}:")
print(f"- GDP Growth Rate: {best_region['GDP_growth']:.2f}%")
print(f"- Unemployment Rate: {best_region['unemployment_rate']:.2f}%")
print(f"- Investment Score: {best_region['investment_score']:.2f}")
print(f"- Education Index: {best_region['education_index']:.2f}")
print(f"- Infrastructure Quality: {best_region['infrastructure_quality']:.2f}")
```

    The region with the highest economic growth potential is Region A:
    - GDP Growth Rate: 1.66%
    - Unemployment Rate: 3.90%
    - Investment Score: 92.02
    - Education Index: 0.67
    - Infrastructure Quality: 7.56


### problem final

- make an empty list and dictionary
- add data in all of the given simple loops, so that this problem runs its print functions without error
- this one is hard, try very hard, a heartfelt atempt, like all of the code done with minor issues is still full credit

try to understand this problem, it has lots of data abstractions

data is given on the bottem and a function is calling it IMPORTANT!!!



```python
def simulate_data_structure(data):
    city_data = {}  # Dictionary to store city data
    city_stats = []  # List to store city statistics

    for person in data:
        name = person["name"]
        age = person["age"]
        city = person["city"]

        # 1. Create a dictionary of city data
        if city not in city_data:
            city_data[city] = {"names": [], "total_age": 0, "total_people": 0}

        city_data[city]["names"].append(name)
        city_data[city]["total_age"] += age
        city_data[city]["total_people"] += 1

    for city, city_info in city_data.items():
        # 2. Calculate the average age for each city
        average_age = city_info["total_age"] / city_info["total_people"]
        city_info["average_age"] = round(average_age, 2)  # Round to 2 decimal places

        # 3. Create a dictionary for city statistics
        city_stats.append({"city": city, "average_age": city_info["average_age"]})

    # Add the city statistics under the "Statistics" key
    city_data["Statistics"] = city_stats

    return city_data

# Example data
data = [
    {"name": "Alice", "age": 25, "city": "New York"},
    {"name": "Bob", "age": 30, "city": "Los Angeles"},
    {"name": "Charlie", "age": 22, "city": "New York"},
    {"name": "David", "age": 35, "city": "Los Angeles"},
    {"name": "Eve", "age": 28, "city": "Chicago"},
]

result = simulate_data_structure(data)
print(result)
```

    {'New York': {'names': ['Alice', 'Charlie'], 'total_age': 47, 'total_people': 2, 'average_age': 23.5}, 'Los Angeles': {'names': ['Bob', 'David'], 'total_age': 65, 'total_people': 2, 'average_age': 32.5}, 'Chicago': {'names': ['Eve'], 'total_age': 28, 'total_people': 1, 'average_age': 28.0}, 'Statistics': [{'city': 'New York', 'average_age': 23.5}, {'city': 'Los Angeles', 'average_age': 32.5}, {'city': 'Chicago', 'average_age': 28.0}]}

