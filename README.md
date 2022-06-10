# Общая информатика

## Лабораторная работа №2
## Шмыкова Дарья 2105-240502D

### Содержание:

1. Условие задачи
2. Блок-схема
3. Код
4. Описание программы

### 1. Задание:

Сделать программу, вычисляющую произведение двух матриц заданного размера и выводящую результат на экран. Программа должна использовать динамические массивы.

### 2. Блок-схема алгоритма:




### 3. Текст и результат работы программы:

#### Текст программы:

```c++

#include <iostream>     //подключение библиотеки для ввода и вывода
#include <iomanip>      //подключение библиотеки 


using namespace std;

int main() //начало головной программы
{
  //закоментированный вариант работы программы со статическими массивами
  //const int N = 3; //Задаём кол-во строк и стролбцов для матриц
  //const int M = 2;
  //const int K = 3;
  //int A[N][M]; //Задаём матрицу А
  //int B[M][K]; //Задаём матрицу B
  //int C[N][K]; //Задаём матрицу С

    cout << "IDEU" << endl; //объявляем данные о себе и о задаче
    cout << "Shmykova Darya" << endl;
    cout << "Group 2105" << endl;
    cout << "LW number 2" << endl << endl;
    
    int N, M, K;        //объявляем переменные целочисленного типа, для размеров матриц

    cout << "Enter the values for the dimensions of the dimensions of the matrices: " << endl << endl; //вводим данные с клавиатуры
    cout << "N = ";
    cin >> N;
    cout << "M = ";
    cin >> M;
    cout << "K = ";
    cin >> K; //вводим значения с клавиатуры

    int** A = new int* [N];                 //задаём динамический массив, используя указатели, с выделением памяти, для матрицы А размерами NxM
    for (int i = 0; i < N; ++i) A[i] = new int[M];

    int** B = new int* [M];                 //задаём динамический массив, используя указатели, с выделением памяти, для матрицы B размерами MxK
    for (int i = 0; i < M; ++i) B[i] = new int[K];

    int** C = new int* [N];                 //задаём динамический массив, используя указатели, с выделением памяти, для матрицы C размерами NxK
    for (int i = 0; i < N; ++i) C[i] = new int[K];

    cout << endl << " Enter the elements of matrix A:" << endl << endl; //заполняем матрицу

    for (int i = 0; i < N; ++i) {           //цикл for для задания матрицы, где вводим её значения с клавиатуры
        for (int j = 0; j < M; ++j) {
            cout << "A[" << i << ", " << j << "]=";
            cin >> A[i][j];
        }
    }

    cout << endl << endl << "\tMatrix A:" << endl; //выводим на экран получившуюся матрицу А

    for (int i = 0; i < N; ++i) {
        for (int j = 0; j < M; ++j) {
            cout << "\t" << setw(5) << A[i][j];
        }
        cout << endl;
    }
    cout << endl << endl;

    cout << endl << " Enter the elements of matrix B:" << endl << endl;   //цикл for для задания матрицы, где вводим её значения с клавиатуры


    for (int i = 0; i < M; ++i) {
        for (int j = 0; j < K; ++j) {
            cout << "A[" << i << ", " << j << "]=";
            cin >> B[i][j];
        }
    }

    cout << endl << endl << "\tMatrix B:" << endl; //выводим на экран получившуюся матрицу А

    for (int i = 0; i < M; ++i) {
        for (int j = 0; j < K; ++j) {
            cout << "\t" << setw(5) << B[i][j];
        }
        cout << endl;
    }

    cout << endl << endl << " Now let's multiply these matrixes!" << endl << endl << "\tMatrix C=A*B:\n"; //выводим на экран получившееся перемножение

    for (int i = 0; i < N; i++) {           //Цикл перемножения матриц, процесс такой же, как и в матическом перемножении
        for (int j = 0; j < K; j++) {
            C[i][j] = 0;
            for (int l = 0; l < M; l++) {
                C[i][j] += A[i][l] * B[l][j];
            }
            cout << "\t" << setw(5) << C[i][j];
        }
        cout << endl;
    }

    for (int i = 0; i < N; ++i) delete[] A[i];   //очистка помяти из-под массивов
    delete[] A;                                  //delete[] - освобождает память, выделенную оператором new,..
                                                 //..начиная с адреса, на который ссылается указатель 
    for (int i = 0; i < M; ++i) delete[] B[i];
    delete[] B;
    for (int i = 0; i < N; ++i) delete[] C[i];
    delete[] C;

    return 0;     //означает нормальное завершение работы головной программы
}

```

#### Результат работы программы:

![image](https://user-images.githubusercontent.com/100388979/172992904-f240225c-abbe-4968-bcb7-fdb4ed6ff379.png)

### 4. 
