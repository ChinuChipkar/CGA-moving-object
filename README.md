# CGA-moving-object
CGA tourbo c++ moving object

#include <iostream>
#include <chrono>
#include <thread>
#include <cstdlib>

using namespace std;
using namespace std::this_thread;
using namespace std::chrono;

void clearScreen() {
#ifdef _WIN32
    system("cls");
#else
    system("clear");
#endif
}

int main() {
    int width = 50;
    int position = 0;

    while (true) {
        clearScreen();

        for (int i = 0; i < position; ++i)
            cout << " ";
        cout << "*\n";

        sleep_for(milliseconds(100));

        position++;

        if (position >= width)
            position = 0;
    }

    return 0;
}
