#include <iostream>
#include <windows.h>
using namespace std;

void titleScreen();
int main_menu();
void options();

void gotoxy(int x, int y);
char getCharAtxy(short int Cx, short int Cy);

void map();
void house(int Mx, int My);
void tree(int Mx, int My);
void grave(int Mx, int My);

void printMove_entity();

void print_player();
void erase_player();
void movePlayerLeft();
void movePlayerRight();
void movePlayerUp();
void movePlayerDown();

int Px = 60, Py = 22;

int main()
{
    int optionMM;
    titleScreen();
    optionMM = main_menu();
    if (optionMM == 1) 
    {
        map();
        print_player();
        printMove_entity();
    }
    else if (optionMM == 2) {options();}
    else {return 0;}


}

void titleScreen()
{
    system("cls");
    string option;

    cout << "         ____  ____  _   _  ___   _____ _____ ____  ____    _    " << endl;
    cout << "        | ___| / ___|| | | |/ _ \\ |_   _| ____|  _ \\|  _ \\  / \\   " << endl;
    cout << "        ||__ | |    | |_| | | | |  | | |  _| | |_) | |_) |/ _ \\  " << endl;
    cout << "        ||___| |___ |  _  | |_| |  | | | |___|  _ <|  _ </ ___ \\ " << endl;
    cout << "        |____|\\____||_| |_|\\___/   |_| |_____|_| \\_\\_| \\_/_/   \\_\\" << endl;
    cout << endl;
    cout << "                ---==[ ECHOES OF THE FORGOTTEN ]==---" << endl;
    cout << "                                                             v0.2" << endl;
    cout << endl;
    cout << "        ===================================================" << endl;
    cout << "              [ Press Any Key and Enter to Continue ]      " << endl;
    cout << "        ===================================================" << endl;
       
    cin >> option;
}

int main_menu() 
{
    system("cls");
    int option;
    cout << "\n         Select an Option by Entering the Corresponding Number!\n";
    cout << "\n[1] Start the Game...!";
    cout << "\n[2] Options/Preferences...";
    cout << "\n[3] Exit Game...";
    cin >> option;
    return option;
}

void options() 
{
    system("cls");
    cout << "\n       [#]<This Functionality is Still Under Development>[#]";
    Sleep(3000);
    main();
}

void map()
{

    system("cls");
    cout << "\n                 [#]<Loading the playable area...>[#]" << endl;
    Sleep(2000);
    system("cls");
    cout << "\n                          [#]<Enjoy!!!>[#]" << endl;
    Sleep(750);
    system("cls");

    cout << "########################################################################################################################\n";
    cout << "#                                                                                                                      #\n";
    cout << "#                                                                                                                      #\n";
    cout << "#                                                                                                                      #\n";
    cout << "#                                                                                                                      #\n";
    cout << "#                                                                                                                      #\n";
    cout << "#                                                                                                                      #\n";
    cout << "#                                                                                                                      #\n";
    cout << "#                                                                                                                      #\n";
    cout << "#                                                                                                                      #\n";
    cout << "#                                                                                                                      #\n";
    cout << "#                                                                                                                      #\n";
    cout << "#                                                                                                                      #\n";
    cout << "#                                                                                                                      #\n";
    cout << "#                                                                                                                      #\n";
    cout << "#                                                                                                                      #\n";
    cout << "#                                                                                                                      #\n";
    cout << "#                                                                                                                      #\n";
    cout << "#                                                                                                                      #\n";
    cout << "#                                                                                                                      #\n";
    cout << "#                                                                                                                      #\n";
    cout << "#                                                                                                                      #\n";
    cout << "#                                                                                                                      #\n";
    cout << "#                                                                                                                      #\n";
    cout << "#                                                                                                                      #\n";
    cout << "#                                                                                                                      #\n";
    cout << "#                                                                                                                      #\n";
    cout << "#                                                                                                                      #\n";
    cout << "########################################################################################################################\n";

    house(3, 5);
    grave(110, 4);
    tree(90, 3);
    tree(80, 10);
    tree(105, 15);
    tree(20, 18);
    tree(50, 20);
    tree(80, 19);
}

void house(int Mx, int My)
{
    gotoxy(Mx, My);
    cout << "    /\\\\\\\\\\\\\\\\";
    gotoxy(Mx, My + 1);
    cout << "   /         \\\\";
    gotoxy(Mx, My + 2);
    cout << "  /  ________  \\\\";
    gotoxy(Mx, My + 3);
    cout << " |  |   ##   |  | ";
    gotoxy(Mx, My + 4);
    cout << " |  |   ##   |  | ";
    gotoxy(Mx, My + 5);
    cout << " |  | ##  ## |  | ";
    gotoxy(Mx, My + 6);
    cout << " |__|_##__##_|__| ";
}

void tree(int Mx, int My)
{

    gotoxy(Mx, My);
    cout << " /||\\ ";
    gotoxy(Mx, My + 1);
    cout << "/|###\\";
    gotoxy(Mx, My + 2);
    cout << "/|##|\\";
    gotoxy(Mx, My + 3);
    cout << " W##W ";
    gotoxy(Mx, My + 4);
    cout << "  ##  ";
    gotoxy(Mx, My + 5);
    cout << " =##= ";
}

void grave(int Mx, int My)
{
    gotoxy(Mx, My);
    cout << " [-] ";
    gotoxy(Mx, My + 1);
    cout << " |T| ";
    gotoxy(Mx, My + 2);
    cout << " |#| ";
    gotoxy(Mx, My + 3);
    cout << "=|=|=";
}

void printMove_entity()
{

    int Sx = 105, Sy = 2;
    int Vx = 23, Vy = 5;
    int Gx = 23, Gy = 11;

    while (true)
    {
        if (getCharAtxy(Sx, Sy + 4) == ' ')
        {
            Sy++;
        }
        else
        {
            Sy = 2;
        }

        gotoxy(Sx, Sy);
        cout << "\\i/ ";
        gotoxy(Sx, Sy + 1);
        cout << "/#\\";
        gotoxy(Sx, Sy + 2);
        cout << "/ \\";
        Sleep(30);

        gotoxy(Sx, Sy);
        cout << "   ";
        gotoxy(Sx, Sy + 1);
        cout << "   ";
        gotoxy(Sx, Sy + 2);
        cout << "   ";
        Sleep(15);

        if (getCharAtxy(Vx + 3, Vy) == ' ')
        {
            Vx++;
        }
        else
        {
            Vx = 23;
        }

        gotoxy(Vx, Vy);
        cout << " o ";
        gotoxy(Vx, Vy + 1);
        cout << "|#|";
        gotoxy(Vx, Vy + 2);
        cout << "| |";
        Sleep(10);

        gotoxy(Vx, Vy);
        cout << "   ";
        gotoxy(Vx, Vy + 1);
        cout << "   ";
        gotoxy(Vx, Vy + 2);
        cout << "   ";
        Sleep(5);

        if (getCharAtxy(Gx + 3, Gy + 3) == ' ')
        {
            Gx++;
            Gy++;
        }
        else
        {
            Gx = 23;
            Gy = 11;
        }

        gotoxy(Gx, Gy);
        cout << "^o ";
        gotoxy(Gx, Gy + 1);
        cout << "|#\\";
        gotoxy(Gx, Gy + 2);
        cout << "| |";
        Sleep(10);

        gotoxy(Gx, Gy);
        cout << "   ";
        gotoxy(Gx, Gy + 1);
        cout << "   ";
        gotoxy(Gx, Gy + 2);
        cout << "   ";
        Sleep(5);

        if (GetAsyncKeyState(VK_LEFT))
        {
            movePlayerLeft();
        }
        if (GetAsyncKeyState(VK_RIGHT))
        {
            movePlayerRight();
        }
        if (GetAsyncKeyState(VK_UP))
        {
            movePlayerUp();
        }
        if (GetAsyncKeyState(VK_DOWN))
        {
            movePlayerDown();
        }
    }
}

void print_player()
{
    gotoxy(Px, Py);
    cout << " o ";
    gotoxy(Px, Py + 1);
    cout << "/X\\";
}

void erase_player()
{

    gotoxy(Px, Py);
    cout << "   ";
    gotoxy(Px, Py + 1);
    cout << "   ";
}

void movePlayerLeft()
{
    if (getCharAtxy(Px - 1, Py) == ' ' && getCharAtxy(Px - 1, Py + 1) == ' ')
    {
        erase_player();
        Px--;
        print_player();
    }
}
void movePlayerRight()
{
    if (getCharAtxy(Px + 3, Py) == ' ' && getCharAtxy(Px + 3, Py + 1) == ' ')
    {
        erase_player();
        Px++;
        print_player();
    }
}

void movePlayerUp()
{
    if (getCharAtxy(Px, Py - 1) == ' ' && getCharAtxy(Px + 1, Py - 1) == ' ' && getCharAtxy(Px + 2, Py - 1) == ' ' && getCharAtxy(Px + 3, Py - 1) == ' ')
    {
        erase_player();
        Py--;
        print_player();
    }
}

void movePlayerDown()
{
    if (getCharAtxy(Px, Py + 2) == ' ' && getCharAtxy(Px + 1, Py + 2) == ' ' && getCharAtxy(Px + 2, Py + 2) == ' ' && getCharAtxy(Px + 3, Py + 2) == ' ')
    {
        erase_player();
        Py++;
        print_player();
    }
}

void gotoxy(int x, int y)
{
    COORD coord;
    coord.X = x;
    coord.Y = y;
    SetConsoleCursorPosition(GetStdHandle(STD_OUTPUT_HANDLE), coord);
}

char getCharAtxy(short int x, short int y)
{
    CHAR_INFO ci;
    COORD xy = {0, 0};
    SMALL_RECT rect = {x, y, x, y};
    COORD coordBufSize;
    coordBufSize.X = 1;
    coordBufSize.Y = 1;
    return ReadConsoleOutput(GetStdHandle(STD_OUTPUT_HANDLE), &ci, coordBufSize, xy, &rect) ? ci.Char.AsciiChar
                                                                                            : ' ';
}