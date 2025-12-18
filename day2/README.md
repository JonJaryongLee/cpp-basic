- struct

```cpp
#include <iostream>

using namespace std;

struct TestResult
{
    char grade;
    int score;
};

int main()
{
    TestResult tr1, tr2;
    tr1.grade = 'A';
    tr1.score = 100;

    tr2.grade = 'B';
    tr2.score = 80;

    cout << tr1.grade << "\n";
    cout << tr1.score << "\n";
    cout << "\n";
    cout << tr2.grade << "\n";
    cout << tr2.score << "\n";
    return 0;
}
```

- pointer