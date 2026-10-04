# Professional Calculator

This is a command-line calculator I built in Python for Module 4. You type an operation and two numbers, and it gives you the answer. It keeps running until you type `exit`.

This version builds on Module 3 by using object-oriented programming. Each type of calculation is its own class, and a `CalculationFactory` creates the right one based on what you type.

## Features

- Add, subtract, multiply, divide, and power
- `help` shows instructions, `history` shows past calculations, `exit` quits
- Clear error messages for bad input, unknown operations, and dividing by zero
- Uses both LBYL (checking before doing something) and EAFP (trying it and handling the error)
- 100% test coverage, checked automatically by GitHub Actions

## What you need

- Python 3.10 or newer
- Git

## How to set it up

Clone the repo and go into the folder:

```
git clone https://github.com/atharhanjra/assignment4.git
cd assignment4
```

Make a virtual environment and turn it on:

```
python3 -m venv venv
source venv/bin/activate
```

Install what the project needs:

```
pip install -r requirements.txt
```

## How to use it

Start the calculator:

```
python3 main.py
```

Type an operation and two numbers:

```
>> add 10 5
Result: AddCalculation: 10.0 Add 5.0 = 15.0

>> power 2 3
Result: PowerCalculation: 2.0 Power 3.0 = 8.0

>> divide 5 0
Cannot divide by zero.
Please enter a non-zero divisor.

>> history
Calculation History:
1. AddCalculation: 10.0 Add 5.0 = 15.0
2. PowerCalculation: 2.0 Power 3.0 = 8.0

>> exit
Exiting calculator. Goodbye!
```

## How the code is organized

- `app/operation/` has the `Operation` class, which does the actual math
- `app/calculation/` has a class for each type of calculation and the `CalculationFactory` that creates them
- `app/calculator/` has the loop that reads input, handles commands, and prints results
- `tests/` has all the tests, including parameterized tests in `test_calculations.py` and `test_operations.py`
- `main.py` starts the program

## Running the tests

```
pytest tests --cov=app --cov-report=term-missing
```

This runs all the tests and shows how much of the code they cover. The goal is 100%.

## GitHub Actions

Every time I push to GitHub, the tests run automatically. If a test fails or coverage drops below 100%, the build fails.