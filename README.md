# My-Portfolio-
John's Portfolio 
# Arduino Uno: LCD Display with IR Sensor Project

## Project Overview:
In this project, I have created an interactive system that uses an Arduino Uno to control an LCD display, responding to input from an IR sensor. The LCD will display a message when a specific IR signal is detected. This project demonstrates the ability to interface an LCD with an Arduino and handle sensor input to trigger outputs.

## Components Used:
- Arduino Uno
- LCD Display (16x2)
- IR Sensor (TSOP4838)
- Jumper wires
- Breadboard
- Resistors

## Project Objectives:
- Interface the IR sensor with the Arduino Uno.
- Display a specific message on the LCD based on the detected IR signal.
- Program the system to read the IR signal and update the display accordingly.

## Circuit Diagram:
![Circuit Diagram](images/circuit-diagram.png)

## Arduino Code:
```cpp
#include <LiquidCrystal.h>

// Initialize the LCD library with the numbers of the interface pins
LiquidCrystal lcd(12, 11, 5, 4, 3, 2);

int irPin = 7;  // Pin connected to the IR sensor

void setup() {
  lcd.begin(16, 2); // Initialize the LCD
  pinMode(irPin, INPUT);  // Set the IR sensor pin as an input
  lcd.print("Waiting for IR signal...");
}

void loop() {
  int sensorValue = digitalRead(irPin); // Read the IR sensor input

  if (sensorValue == HIGH) {
    lcd.clear();
    lcd.print("IR Signal Detected!");
  } else {
    lcd.clear();
    lcd.print("No Signal");
  }

  delay(100); // Delay for stability
}

---

### **2. Arduino Code** (Code File: `ir_lcd_project.ino`)

Create a `.ino` file (e.g., `ir_lcd_project.ino`) that contains the Arduino code. Here is the code you can use:

```cpp
#include <LiquidCrystal.h>

// Initialize the LCD library with the numbers of the interface pins
LiquidCrystal lcd(12, 11, 5, 4, 3, 2);

// Pin connected to the IR sensor
int irPin = 7;

void setup() {
  lcd.begin(16, 2); // Set up the LCD's number of columns and rows
  pinMode(irPin, INPUT);  // Set the IR sensor pin as an input
  lcd.print("Waiting for IR signal...");
}

void loop() {
  int sensorValue = digitalRead(irPin); // Read the IR sensor input

  // Check if the IR sensor detects a signal
  if (sensorValue == HIGH) {
    lcd.clear();
    lcd.print("IR Signal Detected!");
  } else {
    lcd.clear();
    lcd.print("No Signal");
  }

  delay(100); // Delay to allow sensor to stabilize
}
/my-portfolio
    /images
        circuit-diagram.png
    README.md
    ir_lcd_project.ino
/portfolio
    /projects
        /lcd-ir-project
            /images
                circuit-diagram.png
            README.md
            ir_lcd_project.ino
    /assets
        profile-pic.jpg
    README.md
    index.html (if you want to create a portfolio webpage)
    /resume
        resume.pdf
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My Portfolio</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <header>
    <h1>Welcome to My Portfolio</h1>
  </header>
  <main>
    <section id="about-me">
      <h2>About Me</h2>
      <p>I'm an aspiring engineer and programmer. Here are some of my projects:</p>
    </section>
    <section id="projects">
      <h2>Projects</h2>
      <ul>
        <li>
          <a href="projects/lcd-ir-project/README.md">LCD Display with IR Sensor</a>
          <p>This project demonstrates interfacing an LCD display and IR sensor with an Arduino Uno.</p>
        </li>
      </ul>
    </section>
  </main>
  <footer>
    <p>Contact me: myemail@example.com</p>
  </footer>
</body>
</html>
/* General Styles */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: 'Roboto', sans-serif;
  background-color: #f4f4f4;
  color: #333;
}

h1, h2, h3 {
  color: #222;
}

a {
  text-decoration: none;
  color: inherit;
}

nav {
  background-color: #333;
  padding: 20px;
}

.navbar h1 {
  color: white;
  display: inline-block;
}

.navbar ul {
  list-style-type: none;
  float: right;
}

.navbar ul li {
  display: inline;
  margin-left: 20px;
}

.navbar ul li a {
  color: white;
  font-size: 18px;
}

.navbar ul li a:hover {
  color: #f7a700;
}

/* Introduction Section */
#intro {
  background: #f7a700;
  color: white;
  padding: 50px;
  text-align: center;
}

#intro h2 {
  font-size: 3em;
}

.cta-btn {
  background-color: #222;
  color: white;
  padding: 10px 20px;
  font-size: 16px;
  margin-top: 20px;
  display: inline-block;
  border-radius: 5px;
  text-transform: uppercase;
  transition: background-color 0.3s ease;
}

.cta-btn:hover {
  background-color: #f7a700;
  color: #333;
}

/* Section Styles */
section {
  padding: 50px 20px;
}

.section-content {
  width: 80%;
  margin: 0 auto;
  text-align: center;
}

#projects .project-card {
  display: inline-block;
  width: 30%;
  background-color: white;
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  margin: 20px;
  padding: 20px;
  text-align: center;
}

#projects .project-card img {
  width: 100%;
  border-radius: 5px;
}

#projects .project-card h3 {
  margin-top: 15px;
}

footer {
  background-color: #333;
  color: white;
  text-align: center;
  padding: 20px;
  position: fixed;
  bottom: 0;
  width: 100%;
}
