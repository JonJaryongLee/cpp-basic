- 단축키

Ctrl + F5 : 디버깅 없이 실행  
F5 : 디버깅 있이 실행  
Ctrl + A : 모두선택  
F9 : Break Point  
F10 : 다음라인  
Shift + F5 : 디버그 중단  
F11 : 함수 안으로  

- Hello World!

```cpp
#include <iostream>

int main()
{
    std::cout << "Hello World\n";
}
```

- namespace 사용 (실무에선 권장하지 않지만 코딩테스트 등 편의상 사용할때가 많음)

```cpp
#include <iostream>

using namespace std;

int main()
{
    cout << "Hello World\n";
}
```

- `endl`

```cpp
#include <iostream>

using namespace std;

int main()
{
    cout << "Hello World" << endl;
}
```

- 변수/자료형
  - int : 정수
  - double : 실수
  - char : 문자
  - char[size] : 문자열
  - bool
    - `true == 1`
    - `false == 0`

```cpp
int a = 10;
double b = 3.14;
char c = 'A';
char d[10] = "david";
bool e = true;

cout << "Integer: " << a << '\n';
cout << "Double: " << b << '\n';
cout << "Character: " << c << '\n';
cout << "Character Array: " << d << '\n';
cout << "Boolean: " << e << '\n';
```

- 조건문

```cpp
int number;

cout << "숫자를 입력하세요: ";
cin >> number;

if (number > 0)
{
    cout << "입력한 숫자는 양수입니다.\n";
}
else if (number < 0)
{
    cout << "입력한 숫자는 음수입니다.\n";
}
else
{
    cout << "입력한 숫자는 0입니다.\n";
}
```

- `&&`

```cpp
int age;
int has_license;
cout << "나이를 입력하세요: ";
cin >> age;
cout << "운전 면허증이 있습니까? (있으면 1, 없으면 0 입력): ";
cin >> has_license;

if (age >= 18 && has_license == 1)
{
    cout << "운전할 수 있습니다." << '\n';
}
else
{
    cout << "운전할 수 없습니다." << '\n';
}
```

- `||`

```cpp
int age;
int is_weekend;
cout << "나이를 입력하세요: ";
cin >> age;
cout << "주말입니까? (주말이면 1, 아니면 0 입력): ";
cin >> is_weekend;

if (is_weekend == 1 || age < 18)
{
    cout << "오늘은 출근하지 않아도 됩니다." << '\n';
}
else
{
    cout << "오늘은 출근해야 합니다." << '\n';
}
```

- `!`

```cpp
int is_raining;
cout << "비가 오고 있습니까? (오면 1, 아니면 0 입력): ";
cin >> is_raining;
if (!is_raining) {
    cout << "산책을 할 수 있습니다." << '\n';
} else {
    cout << "안에 있는 것이 좋습니다." << '\n';
}
```

- `for`

```cpp
for (int i = 1; i <= 10; i++)
{
    cout << i << " ";
}
cout << "\n";
```

- 의도의 차이를 알자.

```cpp
for (int i = 0; i < 3; i++)
{
    cout << "세 번 찍힘" << "\n";
}
cout << "\n";

for (int i = 2; i <= 5; i++)
{
    cout << i << " ";
}
cout << "\n";
```

- `break`

```cpp
for (int i = 1; i <= 10; i++)
{
    cout << i << " ";
    if (i == 5)
    {
        break;
    }
}
cout << "\n";
```

- `continue`

```cpp
for (int i = 1; i <= 10; i++)
{
    if (i != 5)
    {
        cout << i << " ";
        continue;
    }
    else
    {
        break;
    }

    // 출력 안됨
    cout << "랄랄라!" << "\n";
}
cout << "\n";
```

- 거꾸로 찍기

```cpp
for (int i = 10; i >= 1; i--)
{
    cout << i << " ";
}
cout << "\n";
```

- `while`

```cpp
int num;

while (true)
{
    cout << "숫자를 입력하세요: ";
    cin >> num;

    // 0 을 입력하면 루프 탈출
    if (num == 0)
    {
        cout << "프로그램을 종료합니다.\n";
        break;
    }

    // 입력한 숫자를 출력
    cout << "입력한 숫자: " << num << "\n";
}
```

- 배열

```cpp
int arr[5] = {1, 2, 3, 4, 5};

// 배열의 모든 요소 출력
for (int i = 0; i < 5; i++)
{
    cout << i << ": " << arr[i] << "\n";
}
```

- char 배열

```cpp
char name[10] = "david";
cout << name << "\n";
cout << name[1] << "\n";
```

- length

```cpp
char name[20] = "David Wilson";

int length = 0;

for (int i = 0; i < 20; i++)
{
    if (name[i] == '\0')
    {
        length = i;
        break;
    }
}

cout << "length: " << length << "\n";
```

- ASCII

```cpp
char name[20] = "David Wilson";

int length = 0;

for (int i = 0; i < 20; i++)
{
    if (name[i] == '\0')
    {
        length = i;
        break;
    }
}

cout << "length: " << length << "\n";

int lower_case_cnt = 0;

for (int i = 0; i < length; i++)
{
    if (name[i] >= 'a' && name[i] <= 'z')
    {
        lower_case_cnt++;
    }
}

int upper_case_cnt = 0;

for (int i = 0; i < length; i++)
{
    if (name[i] >= 65 && name[i] <= 90)
    {
        upper_case_cnt++;
    }
}

cout << lower_case_cnt << " " << upper_case_cnt << "\n";
```

- casting (형변환)

```cpp
char ch = 'A';
int num = 97;

cout << "char: " << ch << "\n";
cout << "int: " << (int)ch << "\n";
cout << "\n";
cout << "num char: " << (char)num << "\n";
cout << "num int: " << num << "\n";
```

- 이차원 배열

```cpp
int MAP[4][4] = {
    1, 1, 1, 1,
    1, 0, 0, 1,
    1, 0, 2, 1,
    1, 1, 1, 1,
};

for (int i = 0; i < 4; i++)
{
    for (int j = 0; j < 4; j++)
    {
        cout << MAP[i][j] << " ";
    }
    cout << "\n";
}
```

- 함수

```cpp
#include <iostream>

using namespace std;

// 두 정수를 더하는 함수
int add(int a, int b)
{
    return a + b;
}

// 정수를 출력하는 함수 (반환값이 없는 경우)
void print_number(int number)
{
    cout << "Number: " << number << "\n";
}

int main()
{
    int result = add(3, 5); // add 함수 호출
    cout << "Result: " << result << "\n";
    print_number(10); // printNumber 함수 호출
    return 0;
}
```

- 전역변수, 지역변수

```cpp
#include <iostream>

using namespace std;

int a = 1;

void func(int b)
{
    a++;
    cout << a << "\n";
    cout << b << "\n";
}

int main()
{
    func(2);

    a++;

    cout << a << "\n";

    return 0;
}
```

- call by value / call by reference

```cpp
#include <iostream>

using namespace std;

void func(int local_a)
{
    local_a = 999;
}

int main()
{
    int a = 1;
    func(a);
    
    cout << a << "\n";
    
    return 0;
}
```

```cpp
#include <iostream>

using namespace std;

void func(int local_arr[3])
{
    local_arr[1] = 999;
}

int main()
{
    int arr[3] = {1, 2, 3};
    func(arr);
    for (int i = 0; i < 3; i++)
    {
        cout << arr[i] << " ";
    }
    cout << "\n";
    
    return 0;
}
```

- initialize

```cpp
#include <iostream>

using namespace std;

// 초기화 안해도 알아서 초기화됨
int num1;
char name1[10];

int main()
{
    // 위험한 사용
    int num2;
    char name2[10];

    // 안전한 사용
    int num3 = 0;
    char name3[10] = {0};

    // 아예 초기화하고 사용
    int num4 = 123;
    char name4[10] = "david"; 

    return 0;
}
```