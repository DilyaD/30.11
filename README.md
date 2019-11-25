/*
Напишите эффективную программу, находящую все числа длины n являющиеся палиндромами.
В комментариях напишите, почему перебор - эффективный
*/
/*Просто выводим подряд все палиндромы длины n*/

#include <iostream>
#include <cmath>

using namespace std;

void printInversed (unsigned long long number)
{
    unsigned int size = 1 + (unsigned int)log10(number);
    unsigned long long inv_number = 0;
    for (int i = 1; i <= size; i++)
    {
        cout << number % 10;
        number /= 10;
    };

}

int main()
{
    unsigned int N;
    cin >> N;
    unsigned long long number = (unsigned long long)pow(10, N/2 - 1) - 1;

    if (N == 1)
    {
        cout<<"0\n1\n2\n3\n4\n5\n6\n7\n8\n9\n";
        return 0;
    };
    if (N % 2 == 0)
    {
        while (number++ < (unsigned long long)pow(10, N/2) - 1)
        {
            cout << number;
            printInversed(number);
            cout << endl;
        };
        return 0;
    };
    if (N % 2 == 1)
    {
        for (unsigned int i = 0; i < 10; i++)
        {
            while (number++ < (unsigned long long)pow(10, N/2) - 1)
            {
                cout << number << i;
                printInversed(number);
                cout << endl;
            };
            number = (unsigned long long)pow(10, N/2 - 1) - 1;
        };
        return 0;
    };

    return 0;
}
