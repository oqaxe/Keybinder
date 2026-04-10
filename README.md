# Keybinder

## Description

Keybinder is a lightweight and cross-platform utility designed for managing and customizing keyboard shortcuts.  It allows users to define custom key combinations to trigger specific actions, improving workflow efficiency and accessibility.  Unlike system-level keybinders, Keybinder operates at the application level, allowing for context-sensitive shortcuts tailored to specific programs. The core principle of Keybinder is to provide a simple, flexible, and extensible solution for keyboard customization without requiring in-depth programming knowledge. It's perfect for power users, developers, and anyone looking to streamline their computer usage.

## Features

*   **Custom Keybindings:** Define custom key combinations (e.g., Ctrl+Shift+A, Alt+F1) to trigger user-defined actions.
*   **Application-Specific Binding:**  Create keybindings that are active only when a specific application is in focus.
*   **Action Types:** Supports a variety of action types, including:
    *   Executing shell commands
    *   Opening files or URLs
    *   Simulating key presses (macros)
    *   Running custom scripts (e.g., Python, Bash)
*   **GUI Configuration:** User-friendly graphical interface for creating, editing, and managing keybindings.
*   **Command-Line Interface (CLI):**  Manage keybindings through a command-line interface for scripting and automation.
*   **Cross-Platform Compatibility:** Works on Windows, macOS, and Linux.
*   **Flexible Configuration:** Keybindings are stored in a human-readable configuration file (e.g., YAML, JSON) for easy editing and backup.
*   **Hot Reloading:** Changes to the configuration file are automatically applied without requiring a restart of Keybinder.
*   **Error Handling & Logging:** Robust error handling and logging to help troubleshoot issues and identify conflicting keybindings.
*   **Extensible Architecture:** Designed to be easily extended with new action types and features through plugins or custom scripts.
*   **Clean UI:** Provides a responsive and intuitive interface for all functionalities.

## Technologies Used

*   **Programming Language:** Python
*   **GUI Framework:** PyQt (or Tkinter, depending on the version – specify which is used for your project)
*   **Configuration Parsing:** YAML (PyYAML) or JSON (json library)
*   **Cross-Platform Library:** `pynput` for global keypress detection and simulation.
*   **CLI Parser:** `argparse` (Python standard library)
*   **Operating System Libraries:** `subprocess` (Python standard library) for running external commands.
*   **Packaging:** `pyinstaller` (or equivalent) for creating executable distributions.

## Installation

### Prerequisites

*   **Python:** Python 3.7 or higher is required.
*   **pip:**  Python's package installer (usually included with Python).

### Installation Steps

1.  **Clone the Repository:**

    ```bash
    git clone [Your Repository URL]
    cd Keybinder
    ```

2.  **Create a Virtual Environment (Recommended):**

    ```bash
    python3 -m venv venv
    source venv/bin/activate  # On Linux/macOS
    venv\Scripts\activate  # On Windows
    ```

3.  **Install Dependencies:**

    ```bash
    pip install -r requirements.txt
    ```
    **(Note:** The `requirements.txt` file should be in the root directory of the repository and list all the Python packages required by Keybinder, such as `PyQt`, `pynput`, `PyYAML`, etc.** Example `requirements.txt` content:
    ```
    PyQt6  # Or PyQt5, depending on the version used
    pynput
    PyYAML
    ```
    )

4.  **Run Keybinder:**

    ```bash
    python main.py  # Or the name of your main script
    ```

### Building from Source (Optional)

If you want to build an executable distribution of Keybinder, you can use `pyinstaller` (or a similar tool):

1.  **Install pyinstaller:**
    ```bash
    pip install pyinstaller
    ```

2.  **Build the executable:**
    ```bash
    pyinstaller --onefile --noconsole main.py  # Adjust options as needed
    ```

    This will create an executable file in the `dist` directory. The `--onefile` option creates a single executable file, and `--noconsole` hides the console window.  Adjust these options according to your needs.  You'll likely want to include an icon file as well, using the `--icon` flag. The specific command may need adjustments depending on the GUI framework used.

### macOS Specific Instructions

*   Grant Accessibility Permissions: Keybinder requires accessibility permissions to monitor global key presses.  Go to *System Preferences* -> *Security & Privacy* -> *Privacy* -> *Accessibility* and grant Keybinder access.

### Linux Specific Instructions

*   Dependencies: Ensure you have the necessary system dependencies installed for `pynput`.  This may include `python3-xlib` or similar packages. Consult the `pynput` documentation for details.

## Usage

After installation, run the Keybinder application. The GUI will allow you to:

*   Create new keybindings, specifying the key combination, application context (if any), and the action to be performed.
*   Edit existing keybindings.
*   Enable or disable keybindings.
*   Import and export keybinding configurations.

The CLI interface can be used for scripting and automation.  Run `python main.py --help` (or equivalent for your main script) to see available commands and options.

## Configuration File

Keybindings are stored in a configuration file (e.g., `config.yaml` or `config.json`).  The exact format depends on the chosen configuration parser.  The file should contain a list of keybinding objects, each with the following properties:

*   `key_combination`:  The key combination to trigger the action (e.g., "Ctrl+Shift+A").
*   `application`: The name of the application the keybinding is active for (optional).
*   `action_type`: The type of action to perform (e.g., "execute_command", "open_file", "simulate_key").
*   `action_data`:  Data specific to the action type (e.g., the command to execute, the file path to open, the key to simulate).

See the example configuration file (`config.example.yaml` or `config.example.json`) for a detailed example.

## Contributing

Contributions are welcome! Please submit pull requests with bug fixes, new features, or improvements to the documentation.  Please follow these guidelines:

*   Write clear and concise code.
*   Provide unit tests for new features.
*   Document your code thoroughly.
*   Follow the project's coding style.

## License

[Choose a license, e.g., MIT License]

Copyright (c) [Year] [Your Name/Organization]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.