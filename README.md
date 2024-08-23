def encrypt(text, shift):
    encrypted_text = ""
    for char in text:
        if char.isalpha():
            shift_amount = 65 if char.isupper() else 97
            encrypted_text += chr((ord(char) - shift_amount + shift) % 26 + shift_amount)
        else:
            encrypted_text += char
    return encrypted_text

def decrypt(text, shift):
    return encrypt(text, -shift)

def main():
    choice = input("Do you want to (e)ncrypt or (d)ecrypt? ")
    message = input("Enter your message: ")
    shift = int(input("Enter the shift value: "))

    if choice.lower() == 'e':
        print("Encrypted message:", encrypt(message, shift))
    elif choice.lower() == 'd':
        print("Decrypted message:", decrypt(message, shift))
    else:
        print("Invalid choice. Please choose 'e' for encryption or 'd' for decryption.")

if __name__ == "__main__":
    main()
