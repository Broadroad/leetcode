# [quickSort](https://www.acwing.com/problem/content/787/)
```cpp
#include <iostream>
using namespace std;

const int N = 100010;
int d[N];
int n;

void quickSort(int left, int right) {
    if (left >= right) return;
    int x = d[(left + right) >> 1], i = left - 1, j = right + 1;
    while (i < j) {
        do i++; while (d[i] < x);
        do j--; while (d[j] > x);
        if (i < j) swap(d[i], d[j]);
    }
    quickSort(left, j);
    quickSort(j + 1, right);
}

int main() {
    cin >> n;
    for (int i = 0; i < n; i++) cin >> d[i];
    
    quickSort(0, n - 1);
    for (int i = 0; i < n; i++) cout << d[i] << " ";
    puts("");
    return 0;
}
```
