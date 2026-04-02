
#include <stdio.h>
#include<stdlib.h>

int main(){
    int *arr;
    int i;

    
    arr = (int*) malloc(3 * sizeof(int));
    if (arr == NULL) {
        printf("Initial memory allocation failed.\n");
        return 1;
    }

    // Assign initial values
    for (i = 0; i < 3; i++) {
        arr[i] = (i + 1) * 10;
    }

    int *temp = (int*) realloc(arr, 5 * sizeof(int));
    if (temp == NULL) {
        printf("Memory reallocation failed.\n");
        free(arr); 
        return 1;
    }
    arr = temp;

    
    arr[3] = 40;
    arr[4] = 50;

    printf("Array elements: ");
    for (i = 0; i < 5; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");

    
    free(arr);
    arr = NULL; 

    return 0;
}


