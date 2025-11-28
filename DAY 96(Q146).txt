//Q146: Create Employee structure with nested Date structure for joining date and print details.
#include <stdio.h>
// Nested Date structure
struct Date {
    int day;
    int month;
    int year;
};
// Employee structure containing Date
struct Employee {
    char name[50];
    int id;
    struct Date joiningDate;
};
int main() {
    struct Employee emp;
    // Input
    printf("Enter Employee Name: ");
    scanf("%s", emp.name);
    printf("Enter Employee ID: ");
    scanf("%d", &emp.id);
    printf("Enter Joining Date (dd mm yyyy): ");
    scanf("%d %d %d", &emp.joiningDate.day, &emp.joiningDate.month, &emp.joiningDate.year);
    // Output
    printf("Name: %s | ID: %d | Joining Date: %02d/%02d/%04d\n",
           emp.name, emp.id,
           emp.joiningDate.day, emp.joiningDate.month, emp.joiningDate.year);
    return 0;
}
