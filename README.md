/*
Напишите функцию вычисляющую праймориал числа. Программа должна работать не более чем за O(n*log log n) шагов.
*/

#include <iostream>
using namespace std;

int main() {
    unsigned long long n, S;
    n = 0;
    S = 1;
    cin >> n;
    bool A[n+1];
    for(unsigned long long i = 0; i < n + 1; i++)
    {
        A[i]=true;
    }
    A[0] = A[1] = false;
    for(unsigned long long i = 2; i<=n ; i++) {
        if (A[i]) {
            S *= i;
            for (unsigned long long q = 2; q*i <= n; q++) {
                A[q*i] = false;
            }

        }
    }
    cout << S;
        return 0;

}
