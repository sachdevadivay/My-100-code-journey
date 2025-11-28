//Q147: Store employee data in a binary file using fwrite() and read using fread().
#include <stdio.h>
#include <stdlib.h>
// Employee structure
struct Employee {
    char name[50];
    int id;
    float salary;
};
int main() {
    struct Employee emp, empRead;
    FILE *fp;
    // Input employee details
    printf("Enter Employee Name: ");
    scanf("%s", emp.name);
    printf("Enter Employee ID: ");
    scanf("%d", &emp.id);
    printf("Enter Employee Salary: ");
    scanf("%f", &emp.salary);
    // Open file for writing in binary mode
    fp = fopen("employee.dat", "wb");
    if (fp == NULL) {
        printf("Error opening file for writing!\n");
        exit(1);
    }
    // Write employee data to file
    fwrite(&emp, sizeof(struct Employee), 1, fp);
    fclose(fp);
    printf("\nEmployee details entered and stored in file.\n");
    // Open file for reading in binary mode
    fp = fopen("employee.dat", "rb");
    if (fp == NULL) {
        printf("Error opening file for reading!\n");
        exit(1);
    }
    // Read employee data from file
    fread(&empRead, sizeof(struct Employee), 1, fp);
    fclose(fp);
    // Display employee data
    printf("\nDisplaying employee data read from file:\n");
    printf("Name: %s | ID: %d | Salary: %.2f\n", empRead.name, empRead.id, empRead.salary);
    return 0;
}
