# cybersecurity 1 task 
create a program that can encrypt and decrypt text using caesar cipher algorithm.a;;ow user to input a message and a shift value to perform encryption and decryption
def encrypt(message, shift):
    encrypted_message = []
    for char in message:
        if char.isalpha():
            shift_amount = shift % 26
            base = ord('A') if char.isupper() else ord('a')
            encrypted_char = chr((ord(char) - base + shift_amount) % 26 + base)
            encrypted_message.append(encrypted_char)
        else:
            encrypted_message.append(char)
    return ''.join(encrypted_message)

def decrypt(encrypted_message, shift):
    return encrypt(encrypted_message, -shift)

def main():
    while True:
        print("Caesar Cipher Program")
        print("1. Encrypt a message")
        print("2. Decrypt a message")
        print("3. Exit")
        
        choice = input("Enter your choice (1/2/3): ")
        
        if choice == '3':
            print("Exiting...")
            break
        
        if choice in ['1', '2']:
            message = input("Enter your message: ")
            shift = int(input("Enter the shift value: "))
            
            if choice == '1':
                encrypted_message = encrypt(message, shift)
                print(f"Encrypted Message: {encrypted_message}")
            elif choice == '2':
                decrypted_message = decrypt(message, shift)
                print(f"Decrypted Message: {decrypted_message}")
        else:
            print("Invalid choice. Please select 1, 2, or 3.")

if __name__ == "__main__":
    main()
