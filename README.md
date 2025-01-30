# Board Rooms App Documentation![Uploading Screenshot 1446-07-30 at 10.57.46 AM.png…]()


## Overview

The Board Rooms App allows users to simplify the scheduling of meeting rooms. The app displays an overview of available and unavailable meeting rooms, allows users to book rooms for specific dates, and view their current bookings.

### Key Features
- View all available and unavailable meeting rooms
- Book a meeting room for a specific date
- View your own bookings ("My bookings")

---

## API Integration

The app interacts with the Airtable API to manage boardrooms, employees, and bookings. Below are the key API endpoints used:

### Endpoints:
- **GET /boardrooms**: Fetches all boardroom records.
- **GET /employees**: Fetches all employee records.
- **GET /bookings**: Fetches all booking records.
- **POST /bookings**: Creates a new booking.
- **PUT /bookings/:id**: Updates an existing booking.
- **DELETE /bookings/:id**: Deletes a booking.

For now, the app is using only the **GET** requests to fetch data, including the list of boardrooms, employees, and bookings.

---

## Implementation

### Login ViewModel
- **validateLogin**: Authenticates the user by checking their job number and password against the employee records in Airtable.
- **Error Handling**: Displays relevant error messages if the connection fails, no data is received, or if there is an issue with decoding the response.

### Booking ViewModel
- **fetchBookings**: Fetches bookings for the currently logged-in user. This method uses Airtable’s `/bookings` endpoint and filters the data accordingly.

### BoardRooms ViewModel
- **fetchBoardRooms**: Retrieves available boardroom data from Airtable using the `/boardrooms` endpoint.

### Data Fetching
- The app uses `URLSession` to send requests to the Airtable API.
- Responses are handled asynchronously, and data is decoded using `JSONDecoder`.

---

## Methodology

The development of this app follows the **Agile** methodology. Iterations are planned to implement features like room booking and employee management. Testing is done through Postman to ensure that the API requests are functioning as expected before integration into the app.

---

## Tools Used

- **Xcode**: IDE for developing the app in Swift.
- **Swift**: Programming language used for iOS development.
- **Postman**: Used to test the Airtable API endpoints before integrating them into the app.
- **Airtable API**: Backend used for managing meeting rooms, employees, and bookings.

---

## Setup & Usage

To run the Board Rooms App:

1. Clone this repository to your local machine.
2. Open the project in **Xcode**.
3. Ensure you have the necessary credentials and API tokens for Airtable in your code.
4. Build and run the app on your iOS device or simulator.
5. Use the app to view and book boardrooms, as well as manage your own bookings.

---

## Future Enhancements

- Implement POST, PUT, and DELETE API calls for creating, updating, and deleting bookings.
- Implement user authentication using more secure methods.
- Add additional features like room availability notifications and booking reminders.
