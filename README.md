# Hotel-management-
Multiple booking details 
rooms = {
    101: "Available",
    102: "Available",
    103: "Available"
}

def view_rooms():
    print("\n--- Room Status ---")
    for room_no, status in rooms.items():
        print(f"Room {room_no}: {status}")

def book_room(room_no):
    if rooms[room_no] == "Available":
        rooms[room_no] = "Booked"
        print(f"Room {room_no} booked successfully!")
    else:
        print("Room already booked!")

def checkout_room(room_no):
    rooms[room_no] = "Available"
    print(f"Room {room_no} is now available.")

while True:
    print("\n--- Hotel Management System ---")
    print("1. View Rooms")
    print("2. Book Room")
    print("3. Checkout Room")
    print("4. Exit")
    
    choice = input("Enter choice: ")

    if choice == "1":
        view_rooms()
    elif choice == "2":
        rn = int(input("Enter room number to book (101-103): "))
        if rn in rooms:
            book_room(rn)
        else:
            print("Invalid room number!")
    elif choice == "3":
        rn = int(input("Enter room number to checkout (101-103): "))
        if rn in rooms:
            checkout_room(rn)
        else:
            print("Invalid room number!")
    elif choice == "4":
        print("Exiting...")
        break
    else:
        print("Invalid choice!")
