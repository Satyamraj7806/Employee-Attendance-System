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
