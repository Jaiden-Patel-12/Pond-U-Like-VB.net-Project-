# Pond-U-Like-Visual Basic Project-

Pond U Like is a standalone application in VB.net Windows Form Application which was developed.

The application has the ability to allow employees to calculate accurate and precise gauges which need to be used for a pond lining, arear of liner gauge needed and the cost of the project. This is done by the employee entering pond dimensions (width, depth, length) as well as customer name and customer reference, This then allows orders to be calculated and saved to a text file which can be viewed from the standalone application. 

---

## Features

- Input pond liner length, width, depth, customer name and customer reference
- Calculate total liner area
- Automatically determine the correct liner gauge
  - GAUGE 1
  - GAUGE 2
- Calculate total project cost
- Input validation for pond dimensions
  - Width and length must be between 0.5 and 10 (range check)
  - Customer name and reference must be present (presence check)
  - Depth must be between 0.5 and 2 (range check)
- Save customer orders to a text file (Order.txt)
- View previously saved customer orders
- Real-time date and time display
- Simple and intuitive Windows Forms interface using buttons, list boxes, text boxes and labels. 

---

## How It Works

1. Enter the pond length, width and depth.
2. Enter the customer's name and reference.
3. Click **Calculate**.
4. The application:
   - Calculates liner area
   - Selects the correct liner gauge
   - Calculates the total cost
5. Click **Save** to store the order.
6. Click **View** to display previous orders.
7. Click **Quit** to close the application.

---

## Technologies Used

- Visual Basic .NET
- Windows Forms
- Visual Studio
- Text File Storage (Order.txt)

---

## Skills Demonstrated

- Object-Oriented Programming
- Windows Forms GUI Development
- Event-Driven Programming
- Input Validation
- File Handling
- Custom Functions
- Selection (If Statements)
- Data Processing
- Variables and Data Types
- User Interface Design
- Software Testing
- Debugging

---

## Validation

The application validates all pond dimensions before calculations are performed.

| Input | Valid Range |
|--------|-------------|
| Length | 0.5 m - 10 m |
| Width | 0.5 m - 10 m |
| Depth | 0.5 m - 2 m |
| Customer Name | Not Null |
| Customer Reference | Not Null |

If an invalid value is entered, an error message is displayed and the user is prompted to enter a valid value.

---

## Possible Future Improvements

Possible future enhancements include:

- Database integration instead of text file storage
- Search for customer orders
- Edit and delete existing orders
- Print quotations
- Export orders as PDF
- Improved user interface
- Customer order history
- Employee Login System

### Application:
<img width="900" height="267" alt="image" src="https://github.com/user-attachments/assets/31330188-4ce2-4267-8b68-d9f792609555" />
<img width="900" height="267" alt="image" src="https://github.com/user-attachments/assets/ebcbac58-1680-406d-9ea9-629b45765a16" />

---

## Author -Jaiden Patel
