#include <iostream>
#include <string>
using namespace std;

// Function to convert a decimal number to binary
string decimalToBinary(int number) {
    string binary = "";
    if (number == 0) return "0";
    while (number > 0) {
        // Prepend the remainder (0 or 1) to the binary string
        binary = char((number % 2) + '0') + binary;
        number /= 2; // Divide number by 2 for next bit
    }
    return binary;
}

// Function to convert a binary string to decimal
int binaryToDecimal(string binaryStr) {
    int decimal = 0;
    for (char bit : binaryStr) {
        // Multiply current total by 2 and add the bit value
        decimal = decimal * 2 + (bit - '0');
    }
    return decimal;
}

// Funtion to convert decimal to Hexadecimal
string decimalToHexadecimal(int number) {
    string hex = "";
    char digits[] = "0123456789ABCDEF";// Hex digits lookup to
    if (number == 0) return "0";
    while (number > 0) {
        // Prepend corresponding hex digit
        hex = digits[number % 16] + hex;
        number /= 16; // Divide number by 16 for next digit
    }
    return hex;
}

// Funton to convert Hexadecimal to Decimal
int hexadecimalToDecimal(string hexStr) {
    int decimal = 0;
    for (char ch : hexStr) {
        // Convert character to its decimal value and accumulate
        if (ch >= '0' && ch <= '9') decimal = decimal * 16 + (ch - '0');
        else if (ch >= 'A' && ch <= 'F') decimal = decimal * 16 + (ch - 'A' + 10);
        else if (ch >= 'a' && ch <= 'f') decimal = decimal * 16 + (ch - 'a' + 10);
    }
    return decimal;
}

int main() {
    int choice;
    while (true) {
         // Display conversion menu
        cout <<"\n Conversion menu";
        cout << "\n1. Convert Decimal to Binary\n";
        cout << "2. Convert Binary to Decimal\n";
        cout << "3. Convert Decimal to Hexadecimal\n";
        cout << "4. Convert Hexadecimal to Decimal\n";
        cout<<"5. Demo (Generate and convert random intergers to binary)";
        cout <<"\n6. Exit\n";
        cout << "Enter choice (1-6): ";
        cin >> choice;

        if (choice == 1) {
            int num; cout << "Enter decimal: "; cin >> num;
            cout << "Binary representation: " << decimalToBinary(num)  << endl;
        }
        else if (choice == 2) {
            string bin; cout << "Enter binary: "; cin >> bin;
            cout << "Decimal: representation " << binaryToDecimal(bin) << endl;
        }
        else if (choice == 3) {
            int num; cout << "Enter decimal: "; cin >> num;
            cout << "Hexadecimal representation: " << decimalToHexadecimal(num) << endl;
        }
        else if (choice == 4) {
            string hex; cout << "Enter hexadecimal: "; cin >> hex;
            cout << "Decimal representation: " << hexadecimalToDecimal(hex) << endl;
        }
        else if (choice == 5) { // Placeholder for demo functionality
            break;
        }
        else {
            cout << "Invalid choice!\n";// Handle invalid input
        }
    }
    return 0;// End of program
