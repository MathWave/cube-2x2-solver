#include <iostream>
#include <queue>
#include <ctime>

class side
{
    
    char positions [4];
    
public:
    
    void SetColors(char first, char second, char third, char forth)
    {
        positions[0] = first;
        positions[1] = second;
        positions[2] = third;
        positions[3] = forth;
    }
    
    bool solved()
    {
        if (positions[0] != positions[1] or positions[0] != positions[2] or positions[0] != positions[3])
            return 0;
        return 1;
    }
    
    char* GetColors()
    {
        return positions;
    }
    
};

class cube
{
    
    side sides[6];
    
public:
    
    bool solved()
    {
        for (int i = 0; i < 6; i++)
            if (!sides[i].solved())
                return 0;
        return 1;
    }
    
    void SetColors()
    {
        std::string s [6] = {"UP", "DOWN", "FRONT", "BACK", "RIGHT", "LEFT"};
        char first, second, third, forth;
        for (int i = 0; i < 6; i++)
        {
            std::cout << "input the " << s[i] << " side: ";
            std::cin >> first >> second >> third >> forth;
            sides[i].SetColors(first, second, third, forth);
        }
    }
    
    void RotateUp()
    {
        side up = sides[0];
        side front = sides[2];
        side back = sides[3];
        side right = sides[4];
        side left = sides[5];
        sides[0].SetColors(up.GetColors()[3], up.GetColors()[0], up.GetColors()[1], up.GetColors()[2]);
        sides[2].SetColors(right.GetColors()[0], right.GetColors()[1], front.GetColors()[2], front.GetColors()[3]);
        sides[3].SetColors(left.GetColors()[0], left.GetColors()[1], back.GetColors()[2], back.GetColors()[3]);
        sides[4].SetColors(back.GetColors()[0], back.GetColors()[1], right.GetColors()[2], right.GetColors()[3]);
        sides[5].SetColors(front.GetColors()[0], front.GetColors()[1], left.GetColors()[2], left.GetColors()[3]);
    }
    
    void RotateDown()
    {
        side down = sides[1];
        side front = sides[2];
        side back = sides[3];
        side right = sides[4];
        side left = sides[5];
        sides[1].SetColors(down.GetColors()[3], down.GetColors()[0], down.GetColors()[1], down.GetColors()[2]);
        sides[2].SetColors(front.GetColors()[0], front.GetColors()[1], left.GetColors()[2], left.GetColors()[3]);
        sides[3].SetColors(back.GetColors()[0], back.GetColors()[1], right.GetColors()[2], right.GetColors()[3]);
        sides[4].SetColors(right.GetColors()[0], right.GetColors()[1], front.GetColors()[2], front.GetColors()[3]);
        sides[5].SetColors(left.GetColors()[0], left.GetColors()[1], back.GetColors()[2], back.GetColors()[3]);
    }
    
    void RotateFront()
    {
        side up = sides[0];
        side down = sides[1];
        side front = sides[2];
        side right = sides[4];
        side left = sides[5];
        sides[0].SetColors(up.GetColors()[0], up.GetColors()[1], left.GetColors()[1], left.GetColors()[2]);
        sides[1].SetColors(right.GetColors()[3], right.GetColors()[0], down.GetColors()[2], down.GetColors()[3]);
        sides[2].SetColors(front.GetColors()[3], front.GetColors()[0], front.GetColors()[1], front.GetColors()[2]);
        sides[4].SetColors(up.GetColors()[3], right.GetColors()[1], front.GetColors()[2], up.GetColors()[2]);
        sides[5].SetColors(left.GetColors()[0], down.GetColors()[0], down.GetColors()[1], left.GetColors()[3]);
    }
    
    void RotateBack()
    {
        side up = sides[0];
        side down = sides[1];
        side back = sides[3];
        side right = sides[4];
        side left = sides[5];
        sides[0].SetColors(right.GetColors()[1], right.GetColors()[2], up.GetColors()[2], up.GetColors()[3]);
        sides[1].SetColors(down.GetColors()[0], down.GetColors()[1], left.GetColors()[3], left.GetColors()[0]);
        sides[3].SetColors(back.GetColors()[3], back.GetColors()[0], back.GetColors()[1], back.GetColors()[2]);
        sides[4].SetColors(right.GetColors()[0], down.GetColors()[2], down.GetColors()[3], right.GetColors()[3]);
        sides[5].SetColors(up.GetColors()[1], left.GetColors()[1], left.GetColors()[2], up.GetColors()[0]);
    }
    
    void RotateRight()
    {
        side up = sides[0];
        side down = sides[1];
        side front = sides[2];
        side back = sides[3];
        side right = sides[4];
        sides[0].SetColors(up.GetColors()[0], front.GetColors()[1], front.GetColors()[2], up.GetColors()[3]);
        sides[1].SetColors(down.GetColors()[0], back.GetColors()[3], back.GetColors()[0], down.GetColors()[3]);
        sides[2].SetColors(front.GetColors()[0], down.GetColors()[1], down.GetColors()[2], front.GetColors()[3]);
        sides[3].SetColors(up.GetColors()[2], back.GetColors()[1], back.GetColors()[2], up.GetColors()[1]);
        sides[4].SetColors(right.GetColors()[3], right.GetColors()[0], right.GetColors()[1], right.GetColors()[2]);
    }
    
    void RotateLeft()
    {
        side up = sides[0];
        side down = sides[1];
        side front = sides[2];
        side back = sides[3];
        side left = sides[5];
        sides[0].SetColors(back.GetColors()[2], up.GetColors()[1], up.GetColors()[2], back.GetColors()[1]);
        sides[1].SetColors(front.GetColors()[0], down.GetColors()[1], down.GetColors()[2], front.GetColors()[3]);
        sides[2].SetColors(up.GetColors()[0], front.GetColors()[1], front.GetColors()[2], up.GetColors()[3]);
        sides[3].SetColors(back.GetColors()[0], down.GetColors()[3], down.GetColors()[0], back.GetColors()[3]);
        sides[5].SetColors(left.GetColors()[3], left.GetColors()[0], left.GetColors()[1], left.GetColors()[2]);
    }
    
    void RotateUpDash()
    {
        side up = sides[0];
        side front = sides[2];
        side back = sides[3];
        side right = sides[4];
        side left = sides[5];
        sides[0].SetColors(up.GetColors()[1], up.GetColors()[2], up.GetColors()[3], up.GetColors()[0]);
        sides[2].SetColors(left.GetColors()[0], left.GetColors()[1], front.GetColors()[2], front.GetColors()[3]);
        sides[3].SetColors(right.GetColors()[0], right.GetColors()[1], back.GetColors()[2], back.GetColors()[3]);
        sides[4].SetColors(front.GetColors()[0], front.GetColors()[1], right.GetColors()[2], right.GetColors()[3]);
        sides[5].SetColors(back.GetColors()[0], back.GetColors()[1], left.GetColors()[2], left.GetColors()[3]);
    }
    
    void RotateDownDash()
    {
        side down = sides[1];
        side front = sides[2];
        side back = sides[3];
        side right = sides[4];
        side left = sides[5];
        sides[1].SetColors(down.GetColors()[1], down.GetColors()[2], down.GetColors()[3], down.GetColors()[0]);
        sides[2].SetColors(front.GetColors()[0], front.GetColors()[1], right.GetColors()[2], right.GetColors()[3]);
        sides[3].SetColors(back.GetColors()[0], back.GetColors()[1], left.GetColors()[2], left.GetColors()[3]);
        sides[4].SetColors(right.GetColors()[0], right.GetColors()[1], back.GetColors()[2], back.GetColors()[3]);
        sides[5].SetColors(left.GetColors()[0], left.GetColors()[1], front.GetColors()[2], front.GetColors()[3]);
    }
    
    void RotateFrontDash()
    {
        side up = sides[0];
        side down = sides[1];
        side front = sides[2];
        side right = sides[4];
        side left = sides[5];
        sides[0].SetColors(up.GetColors()[0], up.GetColors()[1], right.GetColors()[1], right.GetColors()[2]);
        sides[1].SetColors(left.GetColors()[3], left.GetColors()[0], down.GetColors()[2], down.GetColors()[3]);
        sides[2].SetColors(front.GetColors()[1], front.GetColors()[2], front.GetColors()[3], front.GetColors()[0]);
        sides[4].SetColors(down.GetColors()[1], right.GetColors()[1], front.GetColors()[2], down.GetColors()[0]);
        sides[5].SetColors(left.GetColors()[0], up.GetColors()[2], up.GetColors()[3], left.GetColors()[3]);
    }
    
    void RotateBackDash()
    {
        side up = sides[0];
        side down = sides[1];
        side back = sides[3];
        side right = sides[4];
        side left = sides[5];
        sides[0].SetColors(left.GetColors()[0], left.GetColors()[3], up.GetColors()[2], up.GetColors()[3]);
        sides[1].SetColors(down.GetColors()[0], down.GetColors()[1], right.GetColors()[2], right.GetColors()[1]);
        sides[3].SetColors(back.GetColors()[1], back.GetColors()[2], back.GetColors()[3], back.GetColors()[0]);
        sides[4].SetColors(right.GetColors()[0], up.GetColors()[0], up.GetColors()[1], right.GetColors()[3]);
        sides[5].SetColors(down.GetColors()[3], left.GetColors()[1], left.GetColors()[2], down.GetColors()[2]);
    }
    
    void RotateRightDash()
    {
        side up = sides[0];
        side down = sides[1];
        side front = sides[2];
        side back = sides[3];
        side right = sides[4];
        sides[0].SetColors(up.GetColors()[0], back.GetColors()[3], back.GetColors()[0], up.GetColors()[3]);
        sides[1].SetColors(down.GetColors()[0], back.GetColors()[1], back.GetColors()[2], down.GetColors()[3]);
        sides[2].SetColors(front.GetColors()[0], up.GetColors()[1], up.GetColors()[2], front.GetColors()[3]);
        sides[3].SetColors(down.GetColors()[2], back.GetColors()[1], back.GetColors()[2], down.GetColors()[1]);
        sides[4].SetColors(right.GetColors()[1], right.GetColors()[2], right.GetColors()[3], right.GetColors()[0]);
    }
    
    void RotateLeftDash()
    {
        side up = sides[0];
        side down = sides[1];
        side front = sides[2];
        side back = sides[3];
        side left = sides[5];
        sides[0].SetColors(front.GetColors()[0], up.GetColors()[1], up.GetColors()[2], front.GetColors()[3]);
        sides[1].SetColors(back.GetColors()[2], down.GetColors()[1], down.GetColors()[2], back.GetColors()[1]);
        sides[2].SetColors(down.GetColors()[0], front.GetColors()[1], front.GetColors()[2], down.GetColors()[3]);
        sides[3].SetColors(back.GetColors()[0], up.GetColors()[3], up.GetColors()[0], back.GetColors()[3]);
        sides[5].SetColors(left.GetColors()[1], left.GetColors()[2], left.GetColors()[3], left.GetColors()[0]);
    }
    
};

std::string FindTheWay(cube c)
{
    std::queue<std::pair<cube, std::string>> q;
    q.push({c, ""});
    while (1)
    {
        if (q.front().first.solved())
            return q.front().second;
        
        cube tmp;
        
        tmp = q.front().first;
        tmp.RotateUp();
        q.push({tmp, q.front().second + "U "});
        
        tmp = q.front().first;
        tmp.RotateDown();
        q.push({tmp, q.front().second + "D "});
        
        tmp = q.front().first;
        tmp.RotateFront();
        q.push({tmp, q.front().second + "F "});
        
        tmp = q.front().first;
        tmp.RotateBack();
        q.push({tmp, q.front().second + "B "});
        
        tmp = q.front().first;
        tmp.RotateRight();
        q.push({tmp, q.front().second + "R "});
        
        tmp = q.front().first;
        tmp.RotateLeft();
        q.push({tmp, q.front().second + "L "});
        
        tmp = q.front().first;
        tmp.RotateUpDash();
        q.push({tmp, q.front().second + "U' "});
        
        tmp = q.front().first;
        tmp.RotateDownDash();
        q.push({tmp, q.front().second + "D' "});
        
        tmp = q.front().first;
        tmp.RotateFrontDash();
        q.push({tmp, q.front().second + "F' "});
        
        tmp = q.front().first;
        tmp.RotateBackDash();
        q.push({tmp, q.front().second + "B' "});
        
        tmp = q.front().first;
        tmp.RotateRightDash();
        q.push({tmp, q.front().second + "R' "});
        
        tmp = q.front().first;
        tmp.RotateLeftDash();
        q.push({tmp, q.front().second + "L' "});
        
        q.pop();
    }
}

int main()
{
    cube c;
    c.SetColors();
    long start = time(0);
    std::cout << FindTheWay(c) << std::endl;
    long end = time(0);
    std::cout << "Needed time: " << end - start  << " seconds" << std::endl;
}
