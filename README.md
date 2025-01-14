# Work-with-2D-array

Here is how you can switch rows into colums in C++
#include <iostream>
using namespace std;

void transpose(int matrix[3][3], int rows, int cols) {
    int transposed[3][3]; // Матрица за резултата

    for (int i = 0; i < rows; ++i) {
        for (int j = 0; j < cols; ++j) {
            transposed[j][i] = matrix[i][j]; // Разменяме i и j
        }
    }

    // Печат на транспонираната матрица
    cout << "Транспонирана матрица:" << endl;
    for (int i = 0; i < cols; ++i) {
        for (int j = 0; j < rows; ++j) {
            cout << transposed[i][j] << " ";
        }
        cout << endl;
    }
}

int main() {
    int matrix[3][3] = {
        {1, 2, 3},
        {4, 5, 6},
        {7, 8, 9}
    };

    transpose(matrix, 3, 3);

    return 0;
}

Here is how to rotate matrix on 90% 


#include <iostream>
using namespace std;

void rotate90Clockwise(int matrix[3][3], int n) {
    // Транспониране
    for (int i = 0; i < n; ++i) {
        for (int j = i; j < n; ++j) {
            swap(matrix[i][j], matrix[j][i]);
        }
    }

    // Обръщане на редовете
    for (int i = 0; i < n; ++i) {
        for (int j = 0; j < n / 2; ++j) {
            swap(matrix[i][j], matrix[i][n - j - 1]);
        }
    }

    // Печат
    cout << "Матрицата след завъртане на 90 градуса:" << endl;
    for (int i = 0; i < n; ++i) {
        for (int j = 0; j < n; ++j) {
            cout << matrix[i][j] << " ";
        }
        cout << endl;
    }
}

int main() {
    int matrix[3][3] = {
        {1, 2, 3},
        {4, 5, 6},
        {7, 8, 9}
    };

    rotate90Clockwise(matrix, 3);

    return 0;
}


on the other side 

#include <iostream>
using namespace std;

void rotate90CounterClockwise(int matrix[3][3], int n) {
    // Транспониране
    for (int i = 0; i < n; ++i) {
        for (int j = i; j < n; ++j) {
            swap(matrix[i][j], matrix[j][i]);
        }
    }

    // Обръщане на колоните
    for (int j = 0; j < n; ++j) {
        for (int i = 0; i < n / 2; ++i) {
            swap(matrix[i][j], matrix[n - i - 1][j]);
        }
    }

    // Печат
    cout << "Матрицата след завъртане на 90 градуса обратно:" << endl;
    for (int i = 0; i < n; ++i) {
        for (int j = 0; j < n; ++j) {
            cout << matrix[i][j] << " ";
        }
        cout << endl;
    }
}

int main() {
    int matrix[3][3] = {
        {1, 2, 3},
        {4, 5, 6},
        {7, 8, 9}
    };

    rotate90CounterClockwise(matrix, 3);

    return 0;
}
Reverse on the rows 

#include <iostream>
using namespace std;

void reverseRows(int matrix[3][3], int rows, int cols) {
    for (int i = 0; i < rows; ++i) {
        for (int j = 0; j < cols / 2; ++j) {
            swap(matrix[i][j], matrix[i][cols - j - 1]);
        }
    }

    // Печат на матрицата
    cout << "Матрицата след обръщане по редове:" << endl;
    for (int i = 0; i < rows; ++i) {
        for (int j = 0; j < cols; ++j) {
            cout << matrix[i][j] << " ";
        }
        cout << endl;
    }
}

int main() {
    int matrix[3][3] = {
        {1, 2, 3},
        {4, 5, 6},
        {7, 8, 9}
    };

    reverseRows(matrix, 3, 3);

    return 0;
}

reverse on colums 

#include <iostream>
using namespace std;

void reverseColumns(int matrix[3][3], int rows, int cols) {
    for (int j = 0; j < cols; ++j) {
        for (int i = 0; i < rows / 2; ++i) {
            swap(matrix[i][j], matrix[rows - i - 1][j]);
        }
    }

    // Печат на матрицата
    cout << "Матрицата след обръщане по колони:" << endl;
    for (int i = 0; i < rows; ++i) {
        for (int j = 0; j < cols; ++j) {
            cout << matrix[i][j] << " ";
        }
        cout << endl;
    }
}

int main() {
    int matrix[3][3] = {
        {1, 2, 3},
        {4, 5, 6},
        {7, 8, 9}
    };

    reverseColumns(matrix, 3, 3);

    return 0;
}


rotate on 180% 

#include <iostream>
using namespace std;

void rotate180(int matrix[3][3], int rows, int cols) {
    for (int i = 0; i < rows / 2; ++i) {
        for (int j = 0; j < cols; ++j) {
            swap(matrix[i][j], matrix[rows - i - 1][cols - j - 1]);
        }
    }

    // Ако има нечетен брой редове
    if (rows % 2 != 0) {
        int mid = rows / 2;
        for (int j = 0; j < cols / 2; ++j) {
            swap(matrix[mid][j], matrix[mid][cols - j - 1]);
        }
    }

    // Печат
    cout << "Матрицата след завъртане на 180 градуса:" << endl;
    for (int i = 0; i < rows; ++i) {
        for (int j = 0; j < cols; ++j) {
            cout << matrix[i][j] << " ";
        }
        cout << endl;
    }
}

int main() {
    int matrix[3][3] = {
        {1, 2, 3},
        {4, 5, 6},
        {7, 8, 9}
    };

    rotate180(matrix, 3, 3);

    return 0;
}


searching for an element in the matrix

#include <iostream>
using namespace std;

void searchElement(int matrix[3][3], int rows, int cols, int target) {
    bool found = false;

    for (int i = 0; i < rows; ++i) {
        for (int j = 0; j < cols; ++j) {
            if (matrix[i][j] == target) {
                cout << "Елементът " << target << " е намерен на позиция (" << i << ", " << j << ")" << endl;
                found = true;
            }
        }
    }

    if (!found) {
        cout << "Елементът " << target << " не е намерен в матрицата." << endl;
    }
}

int main() {
    int matrix[3][3] = {
        {1, 2, 3},
        {4, 5, 6},
        {7, 8, 9}
    };

    int target;
    cout << "Въведете елемент за търсене: ";
    cin >> target;

    searchElement(matrix, 3, 3, target);

    return 0;
}


Suming all elements

#include <iostream>
using namespace std;

int sumAllElements(int matrix[3][3], int rows, int cols) {
    int totalSum = 0;

    for (int i = 0; i < rows; ++i) {
        for (int j = 0; j < cols; ++j) {
            totalSum += matrix[i][j];
        }
    }

    return totalSum;
}

int main() {
    int matrix[3][3] = {
        {1, 2, 3},
        {4, 5, 6},
        {7, 8, 9}
    };

    int result = sumAllElements(matrix, 3, 3);
    cout << "Сумата на всички елементи е: " << result << endl;

    return 0;
}


suming in fixed row 

#include <iostream>
using namespace std;

int sumRow(int matrix[3][3], int cols, int row) {
    int rowSum = 0;

    for (int j = 0; j < cols; ++j) {
        rowSum += matrix[row][j];
    }

    return rowSum;
}

int main() {
    int matrix[3][3] = {
        {1, 2, 3},
        {4, 5, 6},
        {7, 8, 9}
    };

    int row;
    cout << "Въведете индекс на ред (0-2): ";
    cin >> row;

    if (row >= 0 && row < 3) {
        int result = sumRow(matrix, 3, row);
        cout << "Сумата на елементите в ред " << row << " е: " << result << endl;
    } else {
        cout << "Невалиден индекс на ред." << endl;
    }

    return 0;
}


suming in fixed colum

#include <iostream>
using namespace std;

int sumColumn(int matrix[3][3], int rows, int col) {
    int colSum = 0;

    for (int i = 0; i < rows; ++i) {
        colSum += matrix[i][col];
    }

    return colSum;
}

int main() {
    int matrix[3][3] = {
        {1, 2, 3},
        {4, 5, 6},
        {7, 8, 9}
    };

    int col;
    cout << "Въведете индекс на колона (0-2): ";
    cin >> col;

    if (col >= 0 && col < 3) {
        int result = sumColumn(matrix, 3, col);
        cout << "Сумата на елементите в колона " << col << " е: " << result << endl;
    } else {
        cout << "Невалиден индекс на колона." << endl;
    }

    return 0;
}


sum na diagonal 

#include <iostream>
using namespace std;

int sumMainDiagonal(int matrix[3][3], int n) {
    int diagonalSum = 0;

    for (int i = 0; i < n; ++i) {
        diagonalSum += matrix[i][i];
    }

    return diagonalSum;
}

int main() {
    int matrix[3][3] = {
        {1, 2, 3},
        {4, 5, 6},
        {7, 8, 9}
    };

    int result = sumMainDiagonal(matrix, 3);
    cout << "Сумата на главния диагонал е: " << result << endl;

    return 0;
}


second diagonal 

**#include <iostream>
using namespace std;

int sumSecondaryDiagonal(int matrix[3][3], int n) {
    int diagonalSum = 0;

    for (int i = 0; i < n; ++i) {
        diagonalSum += matrix[i][n - i - 1];
    }

    return diagonalSum;
}

int main() {
    int matrix[3][3] = {
        {1, 2, 3},
        {4, 5, 6},
        {7, 8, 9}
    };

    int result = sumSecondaryDiagonal(matrix, 3);
    cout << "Сумата на вторичния диагонал е: " << result << endl;

    return 0;
}

