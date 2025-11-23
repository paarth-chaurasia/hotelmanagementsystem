# 🏨 HotelManagementSystem

A simple hotel room management program made using Python.  
It lets you check guests in, check them out, and see which rooms are free or occupied.  
All data is saved in a JSON file so the system remembers everything even after closing.

# Hotel Management System (Python)

A simple Hotel Management System created in Python that allows users to manage room bookings. This project includes the ability to check in guests, check them out, and view room availability status. Data is saved automatically using a JSON file.

---

## 🛠 Features

* Check-in a guest to a specific room
* Check-out guests and mark the room as available
* Show list of all rooms
* Show only vacant rooms
* Show only occupied rooms
* Persistent data storage using JSON

---

## 📁 Project Structure

```
📦 Hotel Management System
 ┣ 📄 roomsdata.json
 ┣ 📄 main.py
 ┗ 📄 README.md
```

* **roomsdata.json** → Stores room information (auto-generated)
* **main.py** → Main application script
* **README.md** → Description and instructions

---

## ▶️ How to Run the Program

1. Make sure Python is installed (version 3.6 or above recommended).
2. Clone or download the project files.
3. Open a terminal or command prompt.
4. Run the program using:

```sh
python main.py
```

---

## 🧠 How It Works

* The program initializes 50 rooms (5 floors × 10 rooms each)
* Each room is stored with:

  * Status (vacant/occupied)
  * Guest name
  * Check-in date
  * Check-out date
* All data is stored in a JSON file so progress is saved even after closing the program.

---

## 📌 Future Improvements

* Add billing system
* Add admin login
* GUI using Tkinter or PyQt
* Export guest history report

