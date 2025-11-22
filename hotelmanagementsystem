import json
import os
from datetime import datetime

datafile= "roomsdata.json"

def loadrooms():
    if os.path.exists(datafile):
        with open(datafile) as file:
            try:
                return json.load(file)
            except:
                return {}
    else:
        return {}

def saverooms(rooms): 
    with open(datafile, "w") as file:
        json.dump(rooms, file, indent = 4)

rooms = loadrooms()

if not rooms :
    for floor in range(1,6):
        for room in range(1,11):
            roomnumber = str(floor) + str(room).zfill(2)
            rooms[roomnumber] = { "status" : "vacant",
                                  "guest": "",
                                  "checkin" : "",
                                  "checkout" : ""}

def checkin():
    print("==Check In==")
    room = input("Enter room no. :")
    if room not in rooms:
        print("Wrong room no.")
    elif rooms[room]["status"]== "occupied":
        print("This room is occupied already")
    else:
        guestname = input("Guest name :")
        checkindate=str(datetime.now().date())
        rooms[room]["status"] = "occupied"
        rooms[room]["guest"] = guestname
        rooms[room]["checkin"] = checkindate
        rooms[room]["checkout"] = ""
        saverooms(rooms)
        print("Checkin done !")

def checkout():
    print("==Check Out==")
    room = input("Enter room no. :")
    if room not in rooms:
        print("Wrong room no,")
        return
    if rooms[room]["status"] == "vacant":
        print(" The room is already empty")
    else:
        checkoutdate=str(datetime.now().date())
        rooms[room]["status"] = "vacant"
        rooms[room]["guest"] = ""
        rooms[room]["checkout"] = checkoutdate
        rooms[room]["checkin"] = ""
        saverooms(rooms)
        print("Checkout done !")

def show_all_rooms():
    print("==ALL ROOMS==")
    for roomnumber,info in rooms.items():
        print(f"Room {roomnumber} - {info['status']}")

def show_vacant_rooms():
    print("== VACANT ROOMS ==")
    found = False
    for roomnumber,info in rooms.items():
        if info["status"].strip() == "vacant":
            print(roomnumber)
            found = True
    if not found:
        print("No Vacant Rooms")

def show_occupied_rooms():
    print("== OCCUPIED ROOMS ==")
    found = False
    for roomnumber,info in rooms.items():
        if info["status"] == "occupied":
            print(f"{roomnumber} - Guest:{info['guest']}")
            found = True
    if not found:
        print("No Occupied Rooms")

def main():
    while True:
        print("== HOTEL MANAGEMENT SYSTEM ==")
        print("1. Check In")
        print("2. Check Out")
        print("3. Show Vacant Rooms")
        print("4. Show Occupied Rooms")
        print("5. Show All Rooms")
        print("6. Exit")

        choose = input("Pick Option :")

        if choose == "1":
            checkin()
        elif choose == "2":
            checkout()
        elif choose == "3":
            show_vacant_rooms()
        elif choose == "4":
            show_occupied_rooms()
        elif choose == "5":
            show_all_rooms()
        elif choose == "6":
            print("Thank You for using this service")
            break
        else:
            print("Wrong Input")

main()
