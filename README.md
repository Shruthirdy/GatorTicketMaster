# Gator Ticket Master

## Overview
The Gator Ticket Master program is a seat booking service for gator events. Users utilize this service to secure attendance at a gator event. The program implementation mainly uses important data structures like Binary Min-Heap, RedBlack Tree.

---

## Features
- Reserve seats for users based on priority.
- Manage or add users to a waiting list when seats are not available.
- Cancel seat reservations and assign canceled seats to users in the waiting list.
- Add new seats to the system.
- Release seat reservations for a range of user ids.
- Output the current state of reservations and waitlists.

---

## Project Structure
The project consists of the following classes:

### 1. **CustomMinHeap**
- Manages the waitlist using a Min-Heap structure, prioritizing users by their priority/weights.

### 2. **Element**
- Represents individual elements in the Min-Heap, including user ID and priority.

### 3. **GatorReservationController**
- Processes user commands and coordinates the interactions between various components.

### 4. **GatorTicketMaster**
- Main class to initialize the program, read inputs, and gives the commands to the controller.

### 5. **RedBlackTreeImp**
- Implements a Red-Black Tree to manage reserved seats.

### 6. **ReservationManager**
- Handles all operations related to seat reservations, cancellations, and waitlists.

---

## Usage
1. **Input File**: The program reads commands from an input text file (e.g., `Input.txt`).
2. **Commands Supported**:
   - **Initialize(numSeats)**: Sets up the system with a given number of seats.
   - **Reserve(userId, priority)**: Reserves a seat for a user or adds them to the waitlist if no seats are available.
   - **Cancel(seatId, userId)**: Cancels a user's reservation.
   - **AddSeats(numSeats)**: Adds more seats to the system.
   - **Release(userId1, userId2)**: Releases reservations for users within the given ID range.
   - **Print()**: Outputs the current reservation list.
3. Run the program:
   - Execute the `GatorTicketMaster` main class.
   - Provide the input file as a command-line argument or place it in the expected directory.

---

## Input Format
Commands should be written in the input file (`Input.txt`) in the following format:

```console
Initialize(5)
Available()
Reserve(1, 1)
Reserve(2, 1)
Cancel(1, 1)
Reserve(3, 1)
PrintReservations()
Quit()
```
## Output Format

```console
5 Seats are now available for reservation.
Total Seats Available : 5, Waitlist : 0
User 1 reserved seat 1
User 2 reserved seat 2
User 1 canceled their reservation.
User 3 reserved seat 1
[ seat 1, user 3 ]
[ seat 2, user 2 ]
Program Terminated!
```



