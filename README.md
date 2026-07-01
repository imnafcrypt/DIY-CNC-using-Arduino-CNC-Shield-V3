# DIY-CNC-using-Arduino-CNC-Shield-V3

## 💻 Software & Firmware Dependencies
* **[GRBL (v1.1)](https://github.com/grbl/grbl):** An open-source, high-performance software for controlling the motion of machines that move, make things, or both.
* **[Universal G-Code Sender (UGS)](https://github.com/winder/Universal-G-Code-Sender):** A cross-platform Java application to send G-Code to GRBL-based CNC machines.
* **Arduino IDE:** Used to flash the GRBL firmware onto the Arduino.

## 🚀 Installation & Setup

### 1. Hardware Assembly
1. Carefully plug the CNC Shield V3 onto the top of the Arduino Uno.
2. Insert the A4988/DRV8825 stepper drivers into the X, Y, and Z sockets on the shield. **Warning:** Ensure the orientation is correct (usually the potentiometer faces the bottom/USB side), or you risk destroying the drivers.
3. Connect the NEMA 17 stepper motors to the 4-pin headers next to each driver.
4. Wire the 12V/24V power supply to the main power terminal on the CNC shield. **Do not power the motors via the Arduino's 5V/USB.**

### 2. Flashing GRBL Firmware
1. Download the source code from the [GRBL GitHub Repository](https://github.com/grbl/grbl).
2. Extract the `.zip` file.
3. Open the **Arduino IDE**, navigate to `Sketch` -> `Include Library` -> `Add .ZIP Library...` and select the `grbl` folder inside the extracted directory.
4. Open the GRBL upload sketch via `File` -> `Examples` -> `grbl` -> `grblUpload`.
5. Select your Arduino Uno board and COM port, then click **Upload**.

### 3. Configuring Universal G-Code Sender (UGS)
1. Download the latest release from the [UGS GitHub Repository](https://github.com/winder/Universal-G-Code-Sender).
2. Extract and run the application (`ugsplatform`).
3. In the top left connection window:
   * **Firmware:** Select `GRBL`
   * **Port:** Select your Arduino's COM port
   * **Baud:** Select `115200`
4. Click **Connect**. You should hear the stepper motors lock, and the console will display the GRBL startup text (e.g., `Grbl 1.1h ['$' for help]`).
