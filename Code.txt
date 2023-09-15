#include <bits/stdc++.h>
using namespace std;

class Chandraqaan3
{
private:
    int p, q, r;    // Current position (p, q, r)
    char direction; // Current direction (N, S, E, W, U, D)
    char origin;

public:

    // Declaring Constructor Chandraqaan3 with p,q,r co-ordinates and directon.
    Chandraqaan3(int &initialp, int &initialq, int &initialr, char &initialDirection, char org)
    {
        p = initialp;
        q = initialq;
        r = initialr;
        direction = initialDirection;
        origin = org;
    }

    // Backward Chandraqaan3
    void Backward() // b
    {
        switch (direction)
        {
        case 'N':
            q--;
            break;
        case 'S':
            q++;
            break;
        case 'E':
            p--;
            break;
        case 'W':
            p++;
            break;
        case 'U':
            r--;
            break;
        case 'D':
            r++;
            break;
        }
    }

    // Forward Chandraqaan3
    void Forward() // f
    {
        switch (direction)
        {
        case 'N':
            q++;
            break;
        case 'S':
            q--;
            break;
        case 'E':
            p++;
            break;
        case 'W':
            p--;
            break;
        case 'U':
            r++;
            break;
        case 'D':
            r--;
            break;
        }
    }

    // Chandraqaan3 left
    void goleft() // l
    {
        switch (direction)
        {
        case 'N':
            direction = 'W';
            origin = 'W';
            break;
        case 'S':
            direction = 'E';
            origin = 'E';
            break;
        case 'E':
            direction = 'N';
            origin = 'N';
            break;
        case 'W':
            direction = 'S';
            origin = 'S';
            break;
        case 'D':
            if (origin == 'N')
            {
                direction = 'W';
                origin = 'W';
                break;
            }
            else if (origin == 'S')
            {
                direction = 'E';
                origin = 'E';
                break;
            }
            else if (origin == 'E')
            {
                direction = 'N';
                origin = 'N';
                break;
            }
            else
            {
                direction = 'S';
                origin = 'S';
                break;
            }
        case 'U':
            if (origin == 'N')
            {
                direction = 'W';
                origin = 'W';
                break;
            }
            else if (origin == 'S')
            {
                direction = 'E';
                origin = 'E';
                break;
            }
            else if (origin == 'E')
            {
                direction = 'N';
                origin = 'N';
                break;
            }
            else
            {
                direction = 'S';
                origin = 'S';
                break;
            }
        }
    }

    // Chandraqaan3 Right
    void goright() // r
    {

        switch (direction)
        {
        case 'N':
            direction = 'E';
            origin = 'E';
            break;
        case 'S':
            direction = 'W';
            origin = 'W';
            break;
        case 'E':
            direction = 'S';
            origin = 'S';
            break;
        case 'W':
            direction = 'N';
            origin = 'N';
            break;
        case 'D':
            if (origin == 'N')
            {
                direction = 'E';
                origin = 'E';
                break;
            }
            else if (origin == 'S')
            {
                direction = 'W';
                origin = 'W';
                break;
            }
            else if (origin == 'E')
            {
                direction = 'S';
                origin = 'S';
                break;
            }
            else
            {
                direction = 'N';
                origin = 'N';
                break;
            }
        case 'U':
            if (origin == 'N')
            {
                direction = 'E';
                origin = 'E';
                break;
            }
            else if (origin == 'S')
            {
                direction = 'W';
                origin = 'W';
                break;
            }
            else if (origin == 'E')
            {
                direction = 'S';
                origin = 'S';
                break;
            }
            else
            {
                direction = 'N';
                origin = 'N';
                break;
            }
        }
    }

    // Chandraqaan3 Up
    void goup() // u
    {
        if (direction != 'U')
        {
            direction = 'U';
        }
    }

    // Chandraqaan3 Down
    void godown() // d
    {
        if (direction != 'D')
        {
            direction = 'D';
        }
    }

    // p,q,r co-ordinates and direction
    void PrintPosition()
    {
        cout << "Current Position: (" << p << ", " << q << ", " << r << "), Direction: " << direction << endl;
    }

    // Final Position of Chandraqaan3
    void FinalPosition()
    {
        cout << "Final Position: (" << p << ", " << q << ", " << r << ")" << endl;
    }

    // Final Direction of Chandraqaan3
    void FinalDirection()
    {
        cout << "Final Direction: " << direction << endl;
    }
};

int main()
{
    int p = 0, q = 0, r = 0;
    char dir = 'N';
    Chandraqaan3 Craft(p, q, r, dir, 'N');

    string commands;
    cin >> commands;
    cout << endl;

    // Craft.PrintPosition();
    for (int i = 0; i < commands.length(); i++)
    {
        char code = commands[i];
        switch (code)
        {
        case 'f':
            Craft.Forward();
            // Craft.PrintPosition();
            break;
        case 'b':
            Craft.Backward();
            // Craft.PrintPosition();
            break;
        case 'l':
            Craft.goleft();
            // Craft.PrintPosition();
            break;
        case 'r':
            Craft.goright();
            // Craft.PrintPosition();
            break;
        case 'u':
            Craft.goup();
            // Craft.PrintPosition();
            break;
        case 'd':
            Craft.godown();
            // Craft.PrintPosition();
            break;
        }
    }

    // Craft.PrintPosition();
    cout << endl;

    Craft.FinalPosition();
    cout << endl;

    Craft.FinalDirection();
    cout << endl;
    return 0;
}