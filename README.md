# CPSC 352 - Signed Software Release

### Group Members & Contributions
* **Henri Nguyen:** GitHub repo setup, Actions workflow automation, and backend build.
* **Huy Bui:** GPG Key Management and cryptography logic.
* **Kedar Patil:** Testing and documentation.
* **Eric Solorzano:** Testing and documentation.
* **Philip Ma:** Testing and documentation.
* **Kelsey Tang:** Video presentation and demonstration.

---

### How to Verify the Release

**Prerequisites:**
Ensure the following tools are installed on your local device:
1. Git
2. GnuPG (GPG)
*Note: If you are using Windows, you MUST use the **Git Bash** terminal to run the commands below. Ubuntu/Linux users can use the default terminal.*

**Step 1: Get the Public Key**
Clone this repository to your local machine to get the public key needed for verification:
`git clone https://github.com/h3nringuy3n/cpsc352-signed-release.git`

**Step 2: Download the Release Assets**
1. Navigate to the Releases page: https://github.com/h3nringuy3n/cpsc352-signed-release/releases/
2. Download the following three assets into the same directory you just cloned:
   * `hello.exe` *(Note: This is a Windows executable, but Linux users can still verify its integrity).*
   * `SHA256SUMS`
   * `SHA256SUMS.asc`

**Step 3: Import the Public Key**
In your terminal, navigate to the folder containing the downloaded files and run:
`gpg --import public_key.asc`

**Step 4: Verify the Authenticity (Signature)**
Verify that the checksum file was signed by our verified GPG key:
`gpg --verify SHA256SUMS.asc SHA256SUMS`

**Step 5: Verify the Integrity (Checksum)**
Verify that the executable has not been modified since it was compiled:
`sha256sum --check SHA256SUMS --ignore-missing`
