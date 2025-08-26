#include <iostream>
#include <string>
using namespace std;

// Decimal to Binary
string decimalToBinary(int number) {
    string binary = "";
    if (number == 0) return "0";
    while (number > 0) {
        binary = char((number % 2) + '0') + binary;
        number /= 2;
    }
    return binary;
}

// Binary to Decimal
int binaryToDecimal(string binaryStr) {
    int decimal = 0;
    for (char bit : binaryStr) {
        decimal = decimal * 2 + (bit - '0');
    }
    return decimal;
}

// Decimal to Hexadecimal
string decimalToHexadecimal(int number) {
    string hex = "";
    char digits[] = "0123456789ABCDEF";
    if (number == 0) return "0";
    while (number > 0) {
        hex = digits[number % 16] + hex;
        number /= 16;
    }
    return hex;
}

// Hexadecimal to Decimal
int hexadecimalToDecimal(string hexStr) {
    int decimal = 0;
    for (char ch : hexStr) {
        if (ch >= '0' && ch <= '9') decimal = decimal * 16 + (ch - '0');
        else if (ch >= 'A' && ch <= 'F') decimal = decimal * 16 + (ch - 'A' + 10);
        else if (ch >= 'a' && ch <= 'f') decimal = decimal * 16 + (ch - 'a' + 10);
    }
    return decimal;
}

int main() {
    int choice;
    while (true) {
        cout << "\n1. Decimal to Binary\n";
        cout << "2. Binary to Decimal\n";
        cout << "3. Decimal to Hexadecimal\n";
        cout << "4. Hexadecimal to Decimal\n";
        cout << "5. Exit\n";
        cout << "Enter choice: ";
        cin >> choice;

        if (choice == 1) {
            int num; cout << "Enter decimal: "; cin >> num;
            cout << "Binary: " << decimalToBinary(num) << endl;
        }
        else if (choice == 2) {
            string bin; cout << "Enter binary: "; cin >> bin;
            cout << "Decimal: " << binaryToDecimal(bin) << endl;
        }
        else if (choice == 3) {
            int num; cout << "Enter decimal: "; cin >> num;
            cout << "Hexadecimal: " << decimalToHexadecimal(num) << endl;
        }
        else if (choice == 4) {
            string hex; cout << "Enter hexadecimal: "; cin >> hex;
            cout << "Decimal: " << hexadecimalToDecimal(hex) << endl;
        }
        else if (choice == 5) {
            break;
        }
        else {
            cout << "Invalid choice!\n";
        }
    }
    return 0;
