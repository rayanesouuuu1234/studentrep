---
toc: True
comments: True
layout: post
title: Soccer Player Salaries w/ CSV
description: None
courses: {'csp': {'week': 3}}
type: hacks
---

```python
import csv

def get_salary_from_csv(last_name, csv_path='/Users/rayanesouissi/Desktop/mls-salaries-2017.csv'):
    with open(csv_path, mode='r', encoding='utf-8') as file:
        reader = csv.reader(file)
        for row in reader:
            if row[1] == last_name:
                return (row[4], row[5])  # Return tuple of (base salary, guaranteed compensation)
        return None

if __name__ == "__main__":
    player_last_name = input("Enter the player's last name: ")
    salaries = get_salary_from_csv(player_last_name)
    
    if salaries:
        base_salary, guaranteed_compensation = salaries
        print(f"Base Salary for {player_last_name}: ${base_salary}")
        print(f"Guaranteed Compensation for {player_last_name}: ${guaranteed_compensation}")
    else:
        print(f"No player found with last name {player_last_name}.")

```

    Base Salary for Gressel: $75000.0
    Guaranteed Compensation for Gressel: $93750.0

