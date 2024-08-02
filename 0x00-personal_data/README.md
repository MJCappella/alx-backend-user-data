# Personal Data

This project contains tasks for learning to protect a user's personal data.

## Tasks To Complete

+ [x] 0. **Regex-ing**<br/>[filtered_logger.py](filtered_logger.py) contains a function called `filter_datum` that returns the log message obfuscated with the following requirements:
  + Arguments:
    + `fields`: a list of strings representing all fields to obfuscate.
    + `redaction`: a string representing by what the field will be obfuscated.
    + `message`: a string representing the log line.
    + `separator`: a string representing by which character is separating all fields in the log line (`message`).

+ [x] 1. **Log formatter**<br/>[filtered_logger.py](filtered_logger.py).

+ [x] 2. **Create logger**<br/>[filtered_logger.py](filtered_logger.py) contains
  + Uses the file  [user_data.csv](user_data.csv) for this task.
  + Implements a `get_logger` function that takes no arguments and returns a `logging.Logger` object.

+ [x] 3. **Connect to secure database**<br/>[filtered_logger.py](filtered_logger.py) contains the following updates:
  + Implements a `get_db` function that returns a connector to the database (`mysql.connector.connection.MySQLConnection` object).
    + Uses the `os` module to obtain credentials from the environment.
    + Uses the module `mysql-connector-python` to connect to the MySQL database (`pip3 install mysql-connector-python`).

+ [x] 4. **Read and filter data**<br/>[filtered_logger.py](filtered_logger.py) contains a `main` function that takes no arguments and returns nothing with the following requirements:
  + The function will obtain a database connection using `get_db` and retrieve all rows in the `users` table and display each row under a filtered format like this:
    ```log
    [HOLBERTON] user_data INFO 2019-11-19 18:37:59,596: name=***; email=***; phone=***; ssn=***; password=***; ip=e848:e856:4e0b:a056:54ad:1e98:8110:ce1b; last_login=2019-11-14T06:16:24; user_agent=Mozilla/5.0 (compatible; MSIE 9.0; Windows NT 6.1; WOW64; Trident/5.0; KTXN);
    ```
  + Filtered fields:
    + name
    + email
    + phone
    + ssn
    + password
  + Only your `main` function should run when the module is executed.

+ [x] 5. **Encrypting passwords**<br/>[encrypt_password.py](encrypt_password.py) contains a script that meets the following requirements:
  + Implements a `hash_password` function that expects one string argument name password and returns a salted, hashed password, which is a byte string.
  + Uses the `bcrypt` package to perform the hashing (with `hashpw`).

+ [x] 6. **Check valid password**<br/>[app.py](app.py) contains an `is_valid` function that expects 2 arguments and returns a boolean:
  + Arguments:
    + `hashed_password`: `bytes` type.
    + `password`: `str` type.
  + Uses bcrypt to validate that the provided password matches the hashed password.
