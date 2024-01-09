# Python Scaffold

This is a scaffold project designed to help you practice the concepts learned from the Noah Gift YouTube [video](https://www.youtube.com/watch?v=-mdv2wf8yQ8).

## Getting Started

Follow these steps to set up and use the Python scaffold project:

1. **Create a GitHub Repository**

   - Create a new repository on GitHub.
   - Include a `.gitignore` and `README.md` file when creating the repository.

2. **Clone the Repository**

   - Clone the newly created GitHub repository to your local machine or a cloud-based environment like Cloud9.

3. **Create Required Files**

   - Using the terminal, navigate to the repository's directory.
   - Run the following command to create essential files:
     ```bash
     touch Makefile hello.py requirements.txt test_hello.py
     ```

4. **Create a Virtual Environment**

   - Create a virtual environment inside the repository using the following commands:
     ```bash
     python3 -m venv .venv
     source ./.venv/bin/activate
     ```

5. **Edit `requirements.txt`**

   - Open the `requirements.txt` file and add the following Python packages:
     ```yaml
     pylint
     pytest
     click
     black
     pytest-cov
     ```

6. **Edit `Makefile`**

   - Open the `Makefile` and add the following commands for various tasks:

     ```make
     install:
     	pip install --upgrade pip &&\
     		pip install -r requirements.txt

     format:
     	black *.py

     lint:
     	pylint --disable=R,C hello.py

     test:
     	python -m pytest -vv --cov=hello test_hello.py

     all:
     	install lint test
     ```

7. **Edit `hello.py`**

   - Add the following sample code inside the `hello.py` file:

     ```python
     def add(x, y):
         return x + y

     # Uncomment and modify the variables as needed
     # var =
     result = add(1, 2)
     print("This is the sum: 1, 2, %s" % result)
     ```

8. **Edit `test_hello.py`**

   - Add the following code inside the `test_hello.py` file to test the `hello.py` code:

     ```python
     from hello import add

     def test_add():
         assert add(1, 2) == 3
     ```

9. **Install Dependencies**

   - In the terminal, run the following command to install the required Python libraries from the `requirements.txt` file:
     ```bash
     make install
     ```

10. **Code Formatting and Testing**
    - To ensure your `hello.py` code is correctly formatted and tested, run the following commands:
      ```bash
      make format
      make test
      ```

## Folder Architecture

Your project directory should have the following structure:

```
.
├── LICENSE
├── Makefile
├── README.md
├── __pycache__
│   ├── hello.cpython-311.pyc
│   └── test_hello.cpython-311-pytest-7.4.4.pyc
├── hello.py
├── requirements.txt
└── test_hello.py
```

You've now successfully set up and configured your Python scaffold project. You can start building your Python applications while following best practices for code formatting, linting, and testing.
