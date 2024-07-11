#include <iostream>
#include <windows.h>
#include <conio.h> 
using namespace std;
void time();
int cleen(int hr, int min, int sec);
int main() 
{
    for (int MN = 0; MN < 1;)
    {
        int H = 0, h = 0, M = 0, m = 0, S = 0, s = 0, type, i = 0, sign = 0, hh[100], mm[100], ss[100], f = 0;
        for (int m = 0; m < 1;)
        {
            time();
            cout << "To make a stop watch , tap any number\n";
            Sleep(1000);
            if (_kbhit())
            {
                i = _getch() - '0';
                break;
            }
            system("cls");
        }
        system("cls");
        cout << "Hours : "; cin >> H;
        cout << "Minits : "; cin >> M;
        cout << "Secends : "; cin >> S;
        if (S > 60) { while (S > 60) { M += 1; S -= 60; } }
        if (M > 60) { while (M > 60) { H += 1; M -= 60; } }
        system("cls");
        cout << "What type do you want : \n1 > From (00 : 00 : 00) To this time\n2 > From this time to (00 : 00 : 00)\n";
        cin >> type;
        system("cls");
        if (type == 1)
        {
            for (int u = 0; u < 1;)
            {
                cout << "The timer : "; cleen(h, m, s);
                for (int e = 0; e < sign;)
                {
                    while (sign == e + 1)
                    {
                        int x = 0;
                        for (int q = 0; q < sign;)
                        {
                            cout << "\nSign " << x + 1 << " : "; cleen(hh[q], mm[q], ss[q]); q++; x++;
                        }
                        break;
                    }
                    e++;
                }

                cout << "\n\nPause , Tap any number (\"NOT\" > '0') : \n";
                cout << "Do a sign , Tap '0' : ";

                Sleep(950);
                if (_kbhit())
                {
                    i = _getch() - '0';
                    if (i != 0)
                    {
                        system("cls");
                        cleen(h, m, s);
                        cout << "\nResume , Tap any number and press \"enter\" : ";
                        cin >> i;
                    }
                    else { hh[f] = h, mm[f] = m, ss[f] = s; sign++; f++; }
                }
                system("cls");
                s++;
                if (M > 0)
                {
                    if (s == 60) { s = 0; m++; }
                    if (m < M) { if (m == 60) { m = 0; if (H > 0) h++; } }
                    else if (m == M)
                    {
                        if (h == H)
                        {
                            if (s == S)
                            {
                                cleen(h, m, s);

                                if ((time(0) / 3600 + 3) % 24 > 12) { cout << "\a\nTime was ended at : ( " << (time(0) / 3600 + 3) % 24 - 12 << " : " << (time(0) / 60) % 60 << " : " << time(0) % 60 << " )\a"; cout << " PM\n\n"; }
                                else { { cout << "\a\nTime was ended at : ( " << (time(0) / 3600 + 3) % 24 << " : " << (time(0) / 60) % 60 << " : " << time(0) % 60 << " )\a"; cout << " AM\n\n"; } }
                                Sleep(500); cout << "\a"; Sleep(500); cout << "\a\n"; Sleep(3000); u++;
                                    system(cls);
                            }
                        }
                        else u = 0;
                    }
                }
                else if (M == 0)
                {
                    if (s == S)
                    {
                        cleen(h, m, s);
                        if ((time(0) / 3600 + 3) % 24 > 12) { cout << "\a\nTime was ended at : ( " << (time(0) / 3600 + 3) % 24 - 12 << " : " << (time(0) / 60) % 60 << " : " << time(0) % 60 << " )\a"; cout << " PM\n\n"; }
                        else { { cout << "\a\nTime was ended at : ( " << (time(0) / 3600 + 3) % 24 << " : " << (time(0) / 60) % 60 << " : " << time(0) % 60 << " )\a"; cout << " AM\n\n"; } }

                        Sleep(500); cout << "\a"; Sleep(500); cout << "\a\n";  Sleep(3000); u++;
                        system(cls);
                    }

                }

            }

        }
        else if (type == 2)
        {
            for (int u = 0; u < 1;)
            {
                cout << "The timer : "; cleen(H, M, S);
                for (int e = 0; e < sign;)
                {
                    while (sign == e + 1)
                    {
                        int x = 0;
                        for (int q = 0; q < sign;)
                        {
                            cout << "\nSign " << x + 1 << " : "; cleen(hh[q], mm[q], ss[q]); q++; x++;
                        }
                        break;
                    }
                    e++;
                }

                cout << "\n\nPause , Tap any number (\"NOT\" > '0') : \n";
                cout << "Do a sign , Tap '0' : ";
                Sleep(950);

                if (_kbhit())
                {
                    i = _getch() - '0';
                    if (i != 0)
                    {
                        system("cls");
                        cleen(H, M, S);
                        cout << "\nResume , Tap any number and press \"enter\" : ";
                        cin >> i;
                    }
                    else { hh[f] = H, mm[f] = M, ss[f] = S; sign++; f++; }
                }
                Sleep(1000);
                system("cls");
                S--;
                if (S == 0)
                {
                    if (M > 0) { cout << "\a"; M--; S = 59; }
                    else if (M == 0)
                    {
                        if (H == 0)
                        {
                            cout << "( 00 : 00 : 00 )\a\n";
                            if ((time(0) / 3600 + 3) % 24 > 12) { cout << "\a\nTime was ended at : ( " << (time(0) / 3600 + 3) % 24 - 12 << " : " << (time(0) / 60) % 60 << " : " << time(0) % 60 << " )\a"; cout << " PM\n\n"; }
                            else { { cout << "\a\nTime was ended at : ( " << (time(0) / 3600 + 3) % 24 << " : " << (time(0) / 60) % 60 << " : " << time(0) % 60 << " )\a"; cout << " AM\n\n"; } }
                            for (int rr = 0; rr < 6; rr++)
                            {
                                cout << "\a"; Sleep(500);
             
                            }
                            Sleep(3000)
                                u++;
                            system(cls);
                        }
                        else if (H > 0) { cout << "\a"; H--; M = 59; S = 59; }
                    }
                }
            }
        }

    }
}
int cleen(int hr, int min, int sec)
{
    if (hr < 10)
    {
        if (min >= 10 && sec >= 10) { cout << "( 0" << hr << " : " << min << " : " << sec << " )"; }
        else if (min < 10 && sec >= 10) { cout << "( 0" << hr << " : 0" << min << " : " << sec << " )"; }
        else if (min < 10 && sec < 10) { cout << "( 0" << hr << " : 0" << min << " : 0" << sec << " )"; }
        else if (min >= 10 && sec < 10) { cout << "( 0" << hr << " : " << min << " : 0" << sec << " )"; }
    }
    else if (hr >= 10)
    {
        if (min < 10 && sec >= 10) cout << "( " << hr << " : 0" << min << " : " << sec << " )";
        else if (min < 10 && sec < 10) cout << "( " << hr << " : 0" << min << " : 0" << sec << " )";
        else if (min >= 10 && sec < 10) cout << "( " << hr << " : " << min << " : 0" << sec << " )";
        else if (min >= 10 && sec >= 10) cout << "( " << hr << " : " << min << " : " << sec << " )";
    }
    return hr, min, sec;
}
void time()
{
    for(int z=0;z<1;)
    {
        //system("cls");
        cout << "--------------------------------\n";
        if ((time(0) / 3600 + 3) % 24 > 12) { cout << "Now is: ( " << (time(0) / 3600 + 3) % 24 - 12 << " : " << (time(0) / 60) % 60 << " : " << time(0) % 60 << " )"; cout << " PM\n"; }
        else {  cout << "Now is : ( " << (time(0) / 3600 + 3) % 24 << " : " << (time(0) / 60) % 60 << " : " << time(0) % 60 << " )"; cout << " AM\n";  }
        cout << "--------------------------------\n";
        
        break;
    }
}
