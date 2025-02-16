 # Quantum-Random-Number-Generator

This repository contains a Q# implementation of a quantum random number generator. The code demonstrates how to generate random numbers using quantum operations, leveraging the inherent probabilistic nature of quantum mechanics.

## Overview

The main operation, `Main()`, outputs a random integer between 0 and a specified maximum (100 by default). It does so by:
- Generating random bits using a quantum process (via the `GenerateRandomBit()` operation).
- Combining these bits into an integer.
- Recursively retrying if the generated number is outside the desired range.

## Code Structure

The implementation includes the following key operations:

- **`Main()`**  
  Entry point that sets a maximum value, prints a message, and calls `GenerateRandomNumberInRange(max)` to produce a random number.

- **`GenerateRandomNumberInRange(max : Int) : Int`**  
  - Calculates the number of bits (`nBits`) needed to represent `max` using `BitSizeI(max)`.
  - Generates an array of random bits by repeatedly calling `GenerateRandomBit()`.
  - Converts the bit array into an integer with `ResultArrayAsInt(bits)`.
  - Checks if the generated number is within range; if not, it recursively generates a new number.

- **`GenerateRandomBit() : Result`**  
  - Allocates a qubit and applies the Hadamard gate (`H`) to create a superposition.
  - Measures the qubit to obtain a random bit (with equal probability for `0` and `1`).
  - Resets the qubit to the `|0〉` state before deallocation.
  - Returns the measurement result as a `Result`.

## Prerequisites

- [Microsoft Quantum Development Kit (QDK)](https://docs.microsoft.com/en-us/quantum/)
- [.NET Core SDK](https://dotnet.microsoft.com/download) (if using command-line tools)
- [Visual Studio Code](https://code.visualstudio.com/) or another supported IDE configured for Q# development

## Installation

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/ahmeterdempmk/Random-Number-Generator.git
   cd Random-Number-Generator
