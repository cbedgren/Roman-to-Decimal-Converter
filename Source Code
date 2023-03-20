#include <iostream>
#include <vector>
using namespace std;



void checkValidityRoman(string &roman){
    int check=0;

    for (int i = 0; i < roman.length(); i++) {
        if(roman[i]=='I'||roman[i]=='V'||roman[i]=='X'||roman[i]=='L'||roman[i]=='C'||roman[i]=='D'||roman[i]=='M'){
            check+=1;
        }
    }
    if(check==roman.length()){
        for (int i = 0; i < roman.length(); i++) {
            if(roman[i]=='I' && (roman[i+1]=='L'||roman[i+1]=='C'||roman[i+1]=='D'||roman[i+1]=='M')){
                cout << "Please enter a valid Roman Numeral: ";
                cin >> roman;
                cout << endl;
                checkValidityRoman(roman);
            } else if(roman[i]=='V' && (roman[i+1]=='V'||roman[i+1]=='X'||roman[i+1]=='L'||roman[i+1]=='C'||roman[i+1]=='D'||roman[i+1]=='M')){
                cout << "Please enter a valid Roman Numeral: ";
                cin >> roman;
                cout << endl;
                checkValidityRoman(roman);
            } else if(roman[i]=='X' && (roman[i+1]=='D'||roman[i+1]=='M')){
                cout << "Please enter a valid Roman Numeral: ";
                cin >> roman;
                cout << endl;
                checkValidityRoman(roman);
            } else if(roman[i]=='L' && (roman[i]=='L'||roman[i+1]=='C'||roman[i+1]=='D'||roman[i+1]=='M')){
                cout << "Please enter a valid Roman Numeral: ";
                cin >> roman;
                cout << endl;
                checkValidityRoman(roman);
            } else if(roman[i]=='D' && (roman[i+1]=='D'||roman[i+1]=='M')){
                cout << "Please enter a valid Roman Numeral: ";
                cin >> roman;
                cout << endl;
                checkValidityRoman(roman);
            } else if(roman[i]== roman[i+1] && roman[i] == roman[i+2] && roman[i] == roman[i+3]){
                cout << "Please enter a valid Roman Numeral: ";
                cin >> roman;
                cout << endl;
                checkValidityRoman(roman);
            } else if(roman[i] < roman[i+2]){
                cout << "Please enter a valid Roman Numeral: ";
                cin >> roman;
                cout << endl;
                checkValidityRoman(roman);
            }
        }
    } else {
        cout << "Please enter a valid Roman Numeral: ";
        cin >> roman;
        cout << endl;
        checkValidityRoman(roman);
    }
}



void checkValidityInt(int &deci){
    if (deci < 4000 && deci > 0) {
    } else {
        cout << "Please enter a valid decimal number which is less than 4000: ";
        cin >> deci;
        cout << endl;
        checkValidityInt(deci);
    }
}

void romanToInt(string roman, vector<int> &intVec){
    int sum =0;
    for(int i=0; i < roman.length(); i++){
        if(roman[i]=='I'){
            intVec.push_back(1);
        } else if(roman[i]=='V'){
            intVec.push_back(5);
        } else if(roman[i]=='X'){
            intVec.push_back(10);
        } else if(roman[i]=='L'){
            intVec.push_back(50);
        } else if(roman[i]=='C'){
            intVec.push_back(100);
        } else if(roman[i]=='D'){
            intVec.push_back(500);
        } else if(roman[i]=='M'){
            intVec.push_back(1000);
        }
    }

    for(int i=0; i<roman.length(); i++){
        if(intVec[i]>=intVec[i+1]) {
            sum += intVec[i];
        } else {
            sum = intVec[i+1]-intVec[i]+sum;
            i++;
        }
    }
    cout << "We converted your number to decimal: " << sum << endl << endl;
}

void createIntVec(vector<int> &intVec, int deci){
    int num=0;

    if(deci>=1000){
        num = deci / 1000;
        intVec.push_back(num);
    }
    if(deci>=100){
        num = (deci / 100) % 10;
        intVec.push_back(num);
    }
    if(deci>=10){
        num = (deci / 10) % 10;
        intVec.push_back(num);
    }
    if(deci>=0){
        num = deci % 10;
        intVec.push_back(num);
    }

}

void intToRoman(vector<int> intVec,vector<char> romanVec){
    for(int i=0;i<4;i++) {
        if (intVec.size() == 4) {
            while (intVec[i] > 0) {
                romanVec.push_back('M');
                intVec[i] -= 1;
            }
            intVec.pop_back();
        } else if (intVec.size() == 3) {
            if (intVec[i] == 9) {
                romanVec.push_back('C');
                romanVec.push_back('M');
                intVec[i] -= 9;
            } else if (intVec[i] == 4) {
                romanVec.push_back('C');
                romanVec.push_back('D');
                intVec[i] -= 4;
            } else {
                while (intVec[i] > 0) {
                    if (intVec[i] >= 5) {
                        romanVec.push_back('D');
                        intVec[i] -= 5;
                    } else if (intVec[i] > 0) {
                        romanVec.push_back('C');
                        intVec[i] -= 1;
                    }
                }
            }
            intVec.pop_back();
        } else if (intVec.size() == 2) {
            if (intVec[i] == 9) {
                romanVec.push_back('X');
                romanVec.push_back('C');
                intVec[i] -= 9;
            } else if (intVec[i] == 4) {
                romanVec.push_back('X');
                romanVec.push_back('L');
                intVec[i] -= 4;
            } else {
                while (intVec[i] > 0) {
                    if (intVec[i] >= 5) {
                        romanVec.push_back('L');
                        intVec[i] -= 5;
                    } else if (intVec[i] > 0) {
                        romanVec.push_back('X');
                        intVec[i] -= 1;
                    }
                }
            }
            intVec.pop_back();
        } else if (intVec.size() == 1) {
            if (intVec[i] == 9) {
                romanVec.push_back('I');
                romanVec.push_back('X');
                intVec[i] -= 9;
            } else if (intVec[i] == 4) {
                romanVec.push_back('I');
                romanVec.push_back('V');
                intVec[i] -= 4;
            } else {
                while (intVec[i] > 0) {
                    if (intVec[i] >= 5) {
                        romanVec.push_back('V');
                        intVec[i] -= 5;
                    } else if (intVec[i] > 0) {
                        romanVec.push_back('I');
                        intVec[i] -= 1;
                    }
                }
            }
            intVec.pop_back();
        }
    }
    cout << "We converted your number to roman: ";
    for(int i=0;i<romanVec.size();i++) {
        cout << romanVec[i];
    }
    cout << endl;
}

bool numberConverter(){
    string type = "";
    string roman = "";
    int deci = 0;
    vector<int> intVec;
    vector<char> romanVec;

    cout << "Would you like to enter a roman numeral or a decimal number? Please enter \"roman\" or \"decimal\" as your response: ";
    while(type != "roman" || type != "decimal") {
        cin >> type;

        if (type == "roman") {
            cout << "Please enter a roman numeral to convert: ";
            cin >> roman;
            cout << endl;
            checkValidityRoman(roman);
            romanToInt(roman, intVec);
            return true;
        } else if (type == "decimal") {
            cout << "Please enter a decimal number to convert: ";
            cin >> deci;
            cout << endl;
            checkValidityInt(deci);
            createIntVec(intVec, deci);
            intToRoman(intVec, romanVec);
            return true;
        } else {
            cout << "Please enter a valid option: ";
        }
    }
}

int main() {
    numberConverter();
    return 0;
}


/*while(deci >= 1000){
    cout << "deci: " << deci << endl;
    deci = deci - 1000;
    romanVec.push_back('M');
}
while(deci >= 500){
    cout << "deci: " << deci << endl;
    deci = deci - 500;
    romanVec.push_back('D');
}
while(deci >= 100){
    cout << "deci: " << deci << endl;
    deci = deci - 100;
    romanVec.push_back('C');
}
while(deci >= 50){
    cout << "deci: " << deci << endl;
    deci = deci - 50;
    romanVec.push_back('L');
}
while(deci >= 10){
    cout << "deci: " << deci << endl;
    deci = deci - 10;
    romanVec.push_back('X');
}
while(deci >= 5){
    cout << "deci: " << deci << endl;
    deci = deci - 5;
    romanVec.push_back('V');
}
while(deci >= 1){
    cout << "deci: " << deci << endl;
    deci = deci - 1;
    romanVec.push_back('I');
}*/
