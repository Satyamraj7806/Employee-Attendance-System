# Employee-Attendance-System
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

#define MAX_EMPLOYEES 100

struct Employee {
    int id;
    char name[50];
    int attendance;
};

struct Employee employees[MAX_EMPLOYEES];
int totalEmployees = 0;

void addEmployee() {
    if (totalEmployees >= MAX_EMPLOYEES) {
        printf("Employee limit reached!\n");
        return;
    }
    printf("Enter Employee ID: ");
    scanf("%d", &employees[totalEmployees].id);
    printf("Enter Employee Name: ");
    scanf("%s", employees[totalEmployees].name);
    employees[totalEmployees].attendance = 0;
    totalEmployees++;
    printf("Employee added successfully!\n");
}
void markAttendance() {
    int id, i;
    printf("Enter Employee ID to mark attendance: ");
    scanf("%d", &id);
    for (i = 0; i < totalEmployees; i++) {
        if (employees[i].id == id) {
            employees[i].attendance++;
            printf("Attendance marked for %s.\n", employees[i].name);
            return;
        }
    }
    printf("Employee not found!\n");
}

void viewAttendance() {
    printf("\nEmployee Attendance Records:\n");
    printf("ID\tName\tAttendance\n");
    for (int i = 0; i < totalEmployees; i++) {
        printf("%d\t%s\t%d\n", employees[i].id, employees[i].name, employees[i].attendance);
    }
}

int main() {
    int choice;
    while (1) {
        printf("\nEmployee Attendance System\n");
        printf("1. Add Employee\n");
        printf("2. Mark Attendance\n");
        printf("3. View Attendance\n");
        printf("4. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);
        switch (choice) {
            case 1: addEmployee(); break;
            case 2: markAttendance(); break;
            case 3: viewAttendance(); break;
            case 4: exit(0);
            default: printf("Invalid choice!\n");
        }
    }
    return 0;
}

