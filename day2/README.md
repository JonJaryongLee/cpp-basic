- struct

```cpp
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

```cpp
int x = 10;

// x 의 주소를 받을 포인터
int *p;
// 아래와 같이 써도 됨
// int* p

// x : x 의 값
// &x : x 의 주소
// p : x 의 주소
p = &x;
// *p : x 의 값
*p = 20;
// 포인터의 값을 바꿨을 뿐인데 x 가 변경됨!
cout << x << " " << *p << "\n";
```

- pointer (char)

```cpp
char ch = 'A';
char *p;
p = &ch;
*p = 'B';
cout << ch << " " << *p << "\n";
```

- pointer (배열)

```cpp
int arr[3] = {1, 2, 3};
int *g;

// 배열의 0 번째는 시작 주소
g = &arr[0];

// 1 이 아니라, 정해진 타입만큼 주소가 올라감 
*(g + 1) = 999;

for (int i = 0; i < 3; i++)
{
    cout << arr[i] << " ";
}
cout << "\n";

for (int i = 0; i < 3; i++)
{
    cout << *(g + i) << " ";
}
cout << "\n";
```

- 함수와 포인터
  - 함수 안에서 여러 개의 값을 리턴하려고 사용함
  - 실제로는 리턴은 아니고, 주소에 접근해 값 조작

```cpp
// 주소를 포인터로 받음
// void 지만, *p 가 변경되었기에 "리턴" 이라고 표현
void func(int *p)
{
    *p = 10;
}

int main()
{
    int g = 5;
    // 주소를 넣어줌
    func(&g);

    cout << g << "\n";
    return 0;
}
```

```cpp
// 리턴이 없지만, 두 개를 리턴했다고 보는 것
void func(int *pa, int *pb)
{
    *pa = 10;
    *pb = 12;
}

int main()
{
    int a = 5;
    int b = 6;
    // 주소를 넣어줌
    func(&a, &b);

    cout << a << " " << b << "\n";
    return 0;
}
```

- 함수에서 배열을 파라미터로 받는 법 - 1 (배열 사용)

```cpp
// 받는 순간부터, 조사식에서 전체 배열 출력이 안됨
void func(int arr[3])
{
    arr[0] = 3;
    arr[1] = 4;
    arr[2] = 5;
}

int main()
{
    int arr[3] = {1, 2, 3};

    // call by reference 라서 원래 배열이 바뀌어버림!
    func(arr);

    
    for (int i = 0; i < 3; i++)
    {
        cout << arr[i] << " ";
    }
    cout << "\n";

    return 0;
}
```

- 함수에서 배열을 파라미터로 받는 법 - 2 (포인터 사용)

```cpp
// 주소 전달이므로, 포인터로 받기
// 사실 내부적으론 이렇게 처리된다.
void func(int *p)
{
    *(p + 0) = 3;
    *(p + 1) = 4;
    *(p + 2) = 5;
}
```

- 함수에서 배열을 파라미터로 받는 법 - 3 (포인터를 쓰되, 배열처럼 사용)

```cpp
void func(int *arr)
{
    arr[0] = 3;
    arr[1] = 4;
    arr[2] = 5;
}
```

- char 배열을 포인터로 전달

```cpp
void func(char *name)
{
    name[0] = 'D';
}

int main()
{
    char name[20] = "david";
    func(name);
    // 변경됨
    cout << name << "\n";
    return 0;
}
```