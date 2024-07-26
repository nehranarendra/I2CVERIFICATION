# I2CVERIFICATION


Testbench for I2C Interface Verification
Overview
This project contains a SystemVerilog testbench designed to verify the functionality of an I2C interface. The testbench includes multiple components such as a generator, driver, monitor, and scoreboard to facilitate comprehensive verification of the I2C interface.

Directory Structure
src/
i2c_if.sv: I2C interface definition
i2c_top.sv: I2C DUT (Design Under Test)
tb/
i2c_tb.sv: Testbench file containing the test environment
README.md: This file
Testbench Components
Transaction Class
Defines the transaction object with fields for various signals and constraints for randomization.

Generator
Generates random transactions and sends them to the driver via a mailbox.

Driver
Drives the DUT with transactions received from the generator and performs read/write operations.

Monitor
Monitors the DUT's outputs and captures the transaction details.

Scoreboard
Compares the expected outputs with the actual outputs from the DUT to verify correct functionality.

Usage
Clone the repository:

sh
Copy code
git clone [https://github.com/your-repo/i2c-verification.git](https://github.com/nehranarendra/I2CVERIFICATION)
cd i2c-verification
Run the simulation:
Use your preferred simulator to run the testbench. For example, with vcs:

sh
Copy code
vcs -sverilog tb/i2c_tb.sv src/i2c_if.sv src/i2c_top.sv
./simv
View the waveform:
Open the generated dump.vcd file with your preferred waveform viewer to analyze the signals.

Testbench Flow
Initialization:

The clock is initialized and starts toggling.
Mailboxes for communication between components are created.
Pre-test Setup:

The DUT is reset.
Test Execution:

The generator creates random transactions.
The driver drives these transactions to the DUT.
The monitor captures the outputs.
The scoreboard checks the correctness of the DUT's behavior.
Post-test:

The simulation finishes after all transactions are processed.
License
This project is licensed under the MIT License - see the LICENSE file for details.

Contributing
Contributions are welcome! Please open an issue or submit a pull request for any improvements or bug fixes.

