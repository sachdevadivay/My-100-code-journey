//Q150: Use pointer to struct to modify and display data using -> operator.
#include <stdio.h>
#include <stdlib.h>
// Define Student structure
struct Student {
    char name[50];
    int roll;
    int marks;
};
int main() {
    // Dynamically allocate memory for one Student
    struct Student *s = (struct Student *)malloc(sizeof(struct Student));
    if (s == NULL) {
        printf("Memory allocation failed!\n");
        return 1;
    }
    // Modify values using pointer and -> operator
    printf("Enter Student details (Name Roll Marks): ");
    scanf("%s %d %d", s->name, &s->roll, &s->marks);
    // Display modified data
    printf("Modified Data: Name: %s | Roll: %d | Marks: %d\n",
           s->name, s->roll, s->marks);
    // Free allocated memory
    free(s);
    return 0;
}
