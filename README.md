# Control App Access

Control App Access is a lightweight, open-source Windows application that allows you to password-protect specific applications on your computer. It is designed for parents, system administrators, or anyone who wants to restrict access to certain programs.

## Key Features

- **Application Blocking**: Prevent unauthorized access to any executable (`.exe`).
- **Secure Password Protection**: Uses BCrypt hashing to securely store your admin password.
- **Limited vs. Admin Modes**:
    - **Standard Mode**: Blocks most user-level applications.
    - **Admin Mode**: Required to block system-level applications (e.g., Task Manager) and prevent circumvention.
- **Audit Logging**: Keeps a detailed log of all allowed and blocked attempts.
- **Smart Lockout**: Temporarily locks access after too many failed password attempts to prevent brute-forcing.
- **System Tray Integration**: Runs quietly in the background with minimal resource usage.
- **Privacy Focused**: No data is sent to the cloud. Everything stays local on your machine.

## Installation

### Option 1: Self-Installer (Recommended)
1. Download the latest `ControlAppAccess.exe` from the [Releases](https://github.com/yourusername/ControlAppAccess/releases) page.
2. Run the executable.
3. Follow the on-screen instructions to install the app to a permanent location (e.g., `AppData`).
4. **Important**: If prompted, allow the installer to add itself to Windows Defender exclusions to prevent false positives.

### Option 2: Portable
You can run `ControlAppAccess.exe` directly from any folder, but for best results (and to ensure it starts with Windows), we recommend using the installer.

## Usage

1. **Initial Setup**:
   - Upon first launch, you will be asked to set an **Administrator Password**. Do not lose this!
   - You can also set a password hint.

2. **Protecting an App**:
   - Click "Add App" in the main dashboard.
   - Browse and select the `.exe` file you want to protect (e.g., `notepad.exe`, `steam.exe`).
   - The app is now protected! Trying to open it will trigger a password prompt.

3. **Managing Settings**:
   - **Lockout Policy**: Configure how many failed attempts are allowed before a temporary lockout.
   - **Startup**: Choose whether the app starts automatically with Windows.
   - **Notifications**: Toggle desktop notifications for blocked attempts.

## Trust & Antivirus Warnings

Because this application is designed to **intercept and terminate** other processes (the apps you want to block), some Antivirus software (including Windows Defender) may flag it as suspicious.

**This is a False Positive.**

To resolve this:
1. **Submit to Microsoft**: If you encounter a warning, please submit the file to Microsoft as a false positive.
2. **Add Exclusion**: Add the installation folder to your Antivirus exclusions list. The installer can do this for you automatically for Windows Defender.

See [TRUST_GUIDE.md](docs/TRUST_GUIDE.md) for more details.

## Building from Source

**Requirements:**
- .NET 8.0 SDK or later
- Visual Studio 2022 or VS Code

**Steps:**
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/ControlAppAccess.git
   ```
2. Navigate to the project directory:
   ```bash
   cd ControlAppAccess
   ```
3. Build the solution:
   ```bash
   dotnet build --configuration Release
   ```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
