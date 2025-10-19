# Домашнее задание к работе 8

## Условие задачи
Вычислите для заданного натурального n и действительного х с
использованием цикла for значение: sin x + sin x^2 + ... + sin x^n

## 1. Алгоритм и блок-схема

### Алгоритм
1. **Начало**
2. Объявить переменные:
   - `n` — натуральное число (количество слагаемых)
   - `x` — действительное число, основание степени.
   - `sum` — накопитель суммы, инициализирован нулем.
   - `x_power` — будет хранить текущее значение x^i.
3. Ввод данных с клавиатуры.
4. Проверка корректности данных:
   - `if (n <= 0) 
{
    printf("Ошибка: n должно быть натуральным числом!\n");
    return 1;
}`
5. Основной алгоритм - цикл for:
   - `for (int i = 1; i <= n; i++) 
{
    x_power *= x;  
    double sin_value = sin(x_power);  
    sum += sin_value;
    printf("sin(x^%d) = sin(%.4f) = %.6f\n", i, x_power, sin_value);

}`
6. Вывод суммы:
  - `printf("Сумма = %.6f\n", sum);`
7. **Конец**

### Блок-схема



## 2. Реализация программы

#include <stdio.h>
#include <math.h>
#include <locale.h>

int main()
{
    setlocale(LC_ALL, "RUS");
    int n;
    double x;
    double sum = 0.0;
    double x_power = 1.0;

    printf("Введите натуральное число n: ");
    scanf("%d", &n);
    printf("Введите действительное число x: ");
    scanf("%lf", &x);

    if (n <= 0) 
    {
        printf("Ошибка: n должно быть натуральным числом!\n");
        return 1;
    }

    printf("\nВычисление суммы: sin(x) + sin(x^2) + ... + sin(x^%d)\n", n);
    printf("------------------------------------------------\n");

    for (int i = 1; i <= n; i++) 
    {
        x_power *= x;  
        double sin_value = sin(x_power);  
        sum += sin_value;
        printf("sin(x^%d) = sin(%.4f) = %.6f\n", i, x_power, sin_value);
    }

    printf("------------------------------------------------\n");
    printf("Сумма = %.6f\n", sum);

    return 0;
}

## 3. Результаты работы программы

<img width="654" height="243" alt="image" src="https://github.com/user-attachments/assets/7a29472a-8000-4c1d-be99-479e30ae4a83" />

