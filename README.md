#include <iostream>
#include <set>
#include <string>
#include <cstring>
using namespace std;
int factorial(int i)
{
   if (i == 0) return 1;
   else return i*factorial(i - 1);
}
int main()
{
   char chars[] = "pdjugcba";
   //размер массива
   int size = sizeof(chars) / sizeof(chars[0]) - 1; // -1 для отсечения \0 (окончания строки). иначе он будет учитыватся в переборе.
   
   char temp; // переменная для обмена местами элементов
   int count = 0; // счетчик перебора
   // Сортировка массива пузырьком
   for (int i = 0; i < size - 1; i++) {
      for (int j = 0; j < size - i - 1; j++) {
         if (chars[j] > chars[j + 1]) {
            // меняем элементы местами
            temp = chars[j];
            chars[j] = chars[j + 1];
            chars[j + 1] = temp;
            ++count;
         }
      }
   }
   // Вывод массива на экран
   for (int i = 0; i < size; i++) {
      cout << chars[i] << " ";
   }
   cout << endl;
   cout << "Count: " << count << endl;
   cout << "O(n!*n): " << factorial(size) * size << endl;
   return 0;
}
