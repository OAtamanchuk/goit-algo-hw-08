## Description

This repository contains the solution for Homework 8 of the GoIT Python course.
The assignment extends the CLI assistant bot by adding persistent storage for the address book.
The main goal of this project is to ensure that all contact data is saved to disk on program exit and restored automatically on the next launch, so the application does not lose state between sessions.

## Technologies & Stack

The project is implemented using:
- Python 3
- Object-Oriented Programming (OOP)
- Serialization / Deserialization:
   - pickle
- File I/O
- Standard Python libraries:
   - pickle
   - datetime
   - collections.UserDict

## Functionality
**Persistent Address Book**
- The AddressBook object is serialized and saved to a file when the program exits
- On application startup, the address book is automatically restored from the file
- If the data file does not exist, a new empty address book is created

**Core Persistence Functions**
1. save_data(book, filename="addressbook.pkl")
- Serializes the AddressBook object using pickle
- Saves the data to a binary file

2. load_data(filename="addressbook.pkl")
- Loads and deserializes the address book from disk
- Returns a new empty AddressBook if the file does not exist

**CLI Assistant Integration**
- The assistant bot loads saved data at startup
- All contact modifications are preserved automatically
- Before program termination (close / exit), data is saved to disk

**Supported Features (from previous assignments)**
- Contact management (add, edit, delete, search)
- Phone number validation (10 digits)
- Birthday management (DD.MM.YYYY format)
- Upcoming birthdays for the next 7 days
- Error handling using decorators
