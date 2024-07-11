# Building a Virtual Robot Simulator in Python

#### Overview

Welcome to the Virtual Robot Simulator assignment! Your task is to design and implement a virtual robot simulator using Object-Oriented Programming (OOP) principles in Python. You'll create various robot classes with different behaviors and characteristics. The aim is to practice OOP concepts such as classes, inheritance, polymorphism, and encapsulation while being creative in your implementations. 

You will use Git and GitHub for version control and submission, and Docker containers for setting up your development environment. 

#### Problem Statement

#### Part 1: Setup

1. **Repository Setup**
   - Clone the provided repository.
   - Create a new branch for your work.
   - Set up your project directory structure as follows:
     ```
     virtual_robot_simulator/
     ├── Dockerfile
     ├── docker-compose.yml
     ├── README.md
     ├── src/
     │   ├── main.py
     │   └── robots/
     │       ├── __init__.py
     │       ├── base_robot.py
     │       ├── cleaning_robot.py
     │       ├── cooking_robot.py
     │       └── ...
     └── tests/
         ├── test_base_robot.py
         ├── test_cleaning_robot.py
         ├── test_cooking_robot.py
         └── ...
     ```

2. **Docker Setup**
   - Write a `Dockerfile` to create an image for your application.
   - Create a `docker-compose.yml` to manage your containers. (Optional)

#### Part 2: Implementation

1. **Base Class: Robot**
   - Create a base class `Robot` in `base_robot.py` with the following attributes:
     - `name`: string
     - `battery_level`: integer (0 to 100)
     - `status`: string (idle, working, charging)

   - Methods:
     - `charge()`: Increase battery level to 100.
     - `work()`: Abstract method to be implemented by subclasses.
     - `report_status()`: Print the current status of the robot.

2. **Derived Classes (examples, you can add your own)**
   - **CleaningRobot** (`cleaning_robot.py`):
     - Attributes:
       - `cleaning_tool`: string (e.g., vacuum, mop)
     - Methods:
       - `work()`: Implement cleaning behavior. Decrease battery level by 20 for each cleaning session.
   
   - **CookingRobot** (`cooking_robot.py`):
     - Attributes:
       - `cooking_skill`: string (e.g., beginner, intermediate, expert)
     - Methods:
       - `work()`: Implement cooking behavior. Decrease battery level by 30 for each cooking session.
       
**You are encouraged to use DocString and Typing (Research them, very easy to use).**

3. **Polymorphism and Encapsulation**
   - Ensure that all robots can be managed through a common interface.
   - Use getters and setters to access and modify attributes where appropriate.

4. **Main Application**
   - Implement `main.py` to instantiate different robots, perform tasks, and display their status.

#### Part 3: Testing

1. **Unit Tests**
   - Write unit tests for each class in the `tests` directory (Try doing that using `unittest` or `pytest`).
   - Ensure your tests cover different scenarios and edge cases.

#### Part 4: Submission

1. **Git and GitHub**
   - Commit your changes regularly with meaningful commit messages.
   - Push your branch to GitHub.
   - Create a pull request (PR) for review (Optional)

#### Bonus Question (Optional but Encouraged)

**Implementing a Complex Behavior:**

Research and implement a method in the `Robot` class called `self_diagnose()`. This method should perform a self-diagnosis of the robot and report any issues. Consider using advanced OOP concepts such as:

- **Class Methods and Static Methods**: Use these to organize utility functions related to diagnosis.
- **Abstract Base Classes (ABCs)**: Ensure all robot types implement specific diagnostic checks.

Document your research process and explain the advanced OOP concepts you used in your implementation.

#### MaintenanceRobot (`maintenance_robot.py`)

- Inherit from both `CleaningRobot` and `CookingRobot`.
- Implement `multi_task()`: The robot should perform a cleaning task followed by a cooking task.
- Ensure that the `multi_task()` method handles the MRO correctly and avoids any potential issues with attribute or method conflicts.

Document your findings on MRO and how it impacts your implementation in the `README.md` file.
Good luck, and have fun creating your virtual robot simulator!
