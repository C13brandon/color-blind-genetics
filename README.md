#include <iostream>

using namespace std;

// Function asks user to input if the Man is colorblind or not.
void inputCB(double &manVision, double &womanVision);

// Function continues the scenario if Man has normal vision
void MANNORM(double &womanVision);

// Function continues the scenario if Man is colorblind
void MANCB(double &womanVision);

// Function for punnett square: Normal vision man and woman
void PunnettSquareNormalManNormalWoman();

// Function for punnett square: Normal vision man and colorblind woman
void PunnettSquareNormalManColorblindWoman();

// Function for punnett square: Normal vision man and silent carrier woman
void PunnettSquareNormalManSilentCarrierWoman();

// Function for punnett square: Colorblind man and normal vision woman
void PunnettSquareColorblindManNormalWoman();

// Function for punnett square: Colorblind man and colorblind woman
void PunnettSquareColorblindManColorblindWoman();

// Function for punnett square: Colorblind man and silent carrier woman
void PunnettSquareColorblindManSilentCarrierWoman();

int main()
{
    // Variables
    double manVision, womanVision;

    cout << "\nWelcome to Brandon's Colorblind Genetics Program.\n";
    cout << "This program will use genetic data to explore possible inheritance scenarios for children.\n";
    cout << "Please select the options to generate scenarios!\n";
    cout << "______________________________________________________________\n";
    inputCB(manVision, womanVision);

    return 0;
}

void inputCB(double &manVision, double &womanVision) {
    cout << "\n*Use 1 and 2 to answer questions*\n";
    cout << "\nFirst, state the man's eye condition:\n";
    cout << "(1) Normal Vision\n(2) Colorblind\n";
    cin >> manVision;

    while (true) {
        if (manVision != 1 && manVision != 2) {
            cin.clear();
            cin.ignore(10000, '\n');
            cout << "\n*Only 1 and 2 are valid inputs.*\n";
            cout << "State the man's eye condition:\n";
            cout << "(1) Normal Vision\n(2) Colorblind\n";
            cin >> manVision;
        }

        if (manVision == 1) {
            cout << "\nNormal Vision selected.\n";
            MANNORM(womanVision);
            break;
        }
        else if (manVision == 2) {
            cout << "\nColorblindness selected.\n";
            MANCB(womanVision);
            break;
        }
    }
}

void MANNORM(double &womanVision) {
    cout << "\nNow, state the woman's eye condition. A silent carrier option is available:\n";
    cout << "(1) Not Colorblind\n(2) Colorblind\n(3) Silent Carrier\n";
    cin >> womanVision;

    while (true) {
        if (womanVision != 1 && womanVision != 2 && womanVision != 3) {
            cin.clear();
            cin.ignore(10000, '\n');
            cout << "\n*Only 1, 2, and 3 are valid inputs.*\n";
            cout << "State the woman's eye condition:\n";
            cout << "(1) Not Colorblind\n(2) Colorblind\n(3) Silent Carrier\n";
            cin >> womanVision;
        }

        if (womanVision == 1) {
            cout << "Not Colorblind selected.\n";
            PunnettSquareNormalManNormalWoman();
            break;
        }
        else if (womanVision == 2) {
            cout << "Colorblind selected.\n";
            PunnettSquareNormalManColorblindWoman();
            break;
        }
        else if (womanVision == 3) {
            cout << "Silent Carrier selected.\n";
            PunnettSquareNormalManSilentCarrierWoman();
            break;
        }
    }
}

void PunnettSquareNormalManNormalWoman() {
    cout << "\nPunnett Square:\n";
    cout << " --------------------------------\n";
    cout << "| PUNNETT |    XB     |    Y     |\n";
    cout << "|_________|___________|__________|\n";
    cout << "|    XB   |   XBXB    |   XBY    |\n";
    cout << "|_________|___________|__________|\n";
    cout << "|    XB   |   XBXB    |   XBY    |\n";
    cout << " --------------------------------\n";
    cout << "\nPhenotype Distribution:\n";
    cout << "Normal Vision Man: 50%\n";
    cout << "Normal Vision Woman: 50%\n";
    cout << "Colorblind Man: 0%\n";
    cout << "Colorblind Woman: 0%\n";
    cout << "Silent Carrier Woman: 0%\n";
}

void PunnettSquareNormalManColorblindWoman() {
    cout << "\nPunnett Square:\n";
    cout << " --------------------------------\n";
    cout << "| PUNNETT |    XB     |    Y     |\n";
    cout << "|_________|___________|__________|\n";
    cout << "|    Xb   |   XBXb    |   XbY    |\n";
    cout << "|_________|___________|__________|\n";
    cout << "|    Xb   |   XBXb    |   XbY    |\n";
    cout << " --------------------------------\n";
    cout << "\nPhenotype Distribution:\n";
    cout << "Colorblind Man: 50%\n";
    cout << "Silent Carrier Woman: 50%\n";
    cout << "Colorblind Woman: 0%\n";
    cout << "Normal Vision Man: 0%\n";
    cout << "Normal Vision Woman: 0%\n";
}

void PunnettSquareNormalManSilentCarrierWoman() {
    cout << "\nPunnett Square:\n";
    cout << " --------------------------------\n";
    cout << "| PUNNETT |    XB     |    Y     |\n";
    cout << "|_________|___________|__________|\n";
    cout << "|    XB   |   XBXB    |   XBY    |\n";
    cout << "|_________|___________|__________|\n";
    cout << "|    Xb   |   XBXb    |   XbY    |\n";
    cout << " --------------------------------\n";
    cout << "\nPhenotype Distribution:\n";
    cout << "Normal Vision Man: 25%\n";
    cout << "Normal Vision Woman: 25%\n";
    cout << "Colorblind Man: 25%\n";
    cout << "Silent Carrier Man: 25%\n";
    cout << "Colorblind Woman: 0%\n";
}

void MANCB(double &womanVision) {
    cout << "\nNow, state the woman's eye condition. A silent carrier option is available:\n";
    cout << "(1) Not Colorblind\n(2) Colorblind\n(3) Silent Carrier\n";
    cin >> womanVision;

    while (true) {
        if (womanVision != 1 && womanVision != 2 && womanVision != 3) {
            cin.clear();
            cin.ignore(10000, '\n');
            cout << "\n*Only 1, 2, and 3 are valid inputs.*\n";
            cout << "State the woman's eye condition:\n";
            cout << "(1) Not Colorblind\n(2) Colorblind\n(3) Silent Carrier\n";
            cin >> womanVision;
        }

        if (womanVision == 1) {
            cout << "Not Colorblind selected.\n";
            PunnettSquareColorblindManNormalWoman();
            break;
        }
        else if (womanVision == 2) {
            cout << "Colorblind selected.\n";
            PunnettSquareColorblindManColorblindWoman();
            break;
        }
        else if (womanVision == 3) {
            cout << "Silent Carrier selected.\n";
            PunnettSquareColorblindManSilentCarrierWoman();
            break;
        }
    }
}

void PunnettSquareColorblindManNormalWoman() {
    cout << "\nPunnett Square:\n";
    cout << " --------------------------------\n";
    cout << "| PUNNETT |    Xb     |    Y     |\n";
    cout << "|_________|___________|__________|\n";
    cout << "|    XB   |   XBXb    |   XBY    |\n";
    cout << "|_________|___________|__________|\n";
    cout << "|    XB   |   XBXb    |   XBY    |\n";
    cout << " --------------------------------\n";
    cout << "\nPhenotype Distribution:\n";
    cout << "Normal Vision Man: 50%\n";
    cout << "Silent Carrier Woman: 50%\n";
    cout << "Normal Vision Woman: 0%\n";
    cout << "Colorblind Man: 0%\n";
    cout << "Colorblind Woman: 0%\n";
}

void PunnettSquareColorblindManColorblindWoman() {
    cout << "\nPunnett Square:\n";
    cout << " --------------------------------\n";
    cout << "| PUNNETT |    Xb     |    Y     |\n";
    cout << "|_________|___________|__________|\n";
    cout << "|    Xb   |   XbXb    |   XbY    |\n";
    cout << "|_________|___________|__________|\n";
    cout << "|    Xb   |   XbXb    |   XbY    |\n";
    cout << " --------------------------------\n";
    cout << "\nPhenotype Distribution:\n";
    cout << "Colorblind Man: 50%\n";
    cout << "Colorblind Woman: 50%\n";
    cout << "Silent Carrier Woman: 0%\n";
    cout << "Normal Vision Man: 0%\n";
    cout << "Normal Vision Woman: 0%\n";
}

void PunnettSquareColorblindManSilentCarrierWoman() {
    cout << "\nPunnett Square:\n";
    cout << " --------------------------------\n";
    cout << "| PUNNETT |    Xb     |    Y     |\n";
    cout << "|_________|___________|__________|\n";
    cout << "|    XB   |   XBXb    |   XBY    |\n";
    cout << "|_________|___________|__________|\n";
    cout << "|    Xb   |   XbXb    |   XbY    |\n";
    cout << " --------------------------------\n";
    cout << "\nPhenotype Distribution:\n";
    cout << "Normal Vision Man: 25%\n";
    cout << "Colorblind Man: 25%\n";
    cout << "Colorblind Woman: 25%\n";
    cout << "Silent Carrier Woman: 25%\n";
    cout << "Normal Vision Woman: 0%\n";
}
