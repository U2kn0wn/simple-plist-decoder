# plist-decoder

A simple Python tool that **recursively scans a folder for `.plist` files**, decodes them (supports both binary and XML formats), and prints the result in a readable JSON-like format.

Useful during **mobile app pentesting**, **iOS IPA analysis**, or **reverse engineering** to inspect app configuration files such as `Info.plist`, `app metadata`, and privacy usage descriptions.

---

## ✅ Features

- Recursively finds all `.plist` files in a folder
    
- Supports **binary and XML plist formats**
    
- Automatically converts plist objects into readable JSON
    
- Handles dates, bytes, and Apple UID types safely
    
- Prints results cleanly:
    ```
    <Path to plist>
	<Decoded data>
    ```

## 🔧 Requirements

- Python 3.6 or higher
    

---

## 📦 Installation

Clone or download this script and install dependencies (Python’s built-in modules only — no external installs needed):

```
git clone https://github.com/yourusername/plist-decoder.git 
cd plist-decoder
```

---

## ▶️ Usage

Run the script and give it the **folder path** you want to scan:
```
python decode_plists.py /path/to/folder
```
Example:
```
python decode_plists.py extracted_ipa/
```
---

## 💡 Output Example

```
/extracted_ipa/Payload/MyApp.app/Info.plist 
{
   "CFBundleName": "MyApp",   
   "MinimumOSVersion": "14.0",   
   "UIRequiredDeviceCapabilities": [
        "arm64"
    ],   
    "NSCameraUsageDescription": "This app needs camera access." 
}
```

---

## 🔧 Optional Arguments

| Option     | Description          | Default |
| ---------- | -------------------- | ------- |
| `--indent` | Set JSON indent size | 2       |

Example:

```
python decode_plists.py extracted_ipa/ --indent 4
```

---

## 📚 Use Cases

- Inspect iOS app metadata from `.ipa`
    
- Extract privacy strings (`NSCameraUsageDescription`, etc.)
    
- Audit configuration leaks in plist files
    
- Decode plist files during forensic analysis
    

---

## ⚠️ Disclaimer

This script is for educational and security testing purposes only.  
Use it **only on apps and files you own or are authorized to test**.
