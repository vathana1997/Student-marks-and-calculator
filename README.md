# Student-marks-and-calculator
To calculator the marks and total and percentage
#include <stdio.h>

struct Student {
    int rollNo;
    char name[50];
    int marks[5];   // assuming 5 subjects
    int total;
    float average;
};

int main() {
    int i, j, n;
    printf("Enter number of students: ");
    scanf("%d", &n);

    struct Student s[n];

    // Input student details
    for (i = 0; i < n; i++) {
        s[i].total = 0;  // initialize total

        printf("\nEnter details for student %d\n", i + 1);

        printf("Roll Number: ");
        scanf("%d", &s[i].rollNo);

        printf("Name: ");
        scanf("%s", s[i].name);

        printf("Enter marks of 5 subjects: ");
        for (j = 0; j < 5; j++) {
            scanf("%d", &s[i].marks[j]);
            s[i].total += s[i].marks[j];
        }

        s[i].average = s[i].total / 5.0;
    }

    // Display results
    printf("\n--- Student Results ---\n");
    for (i = 0; i < n; i++) {
        printf("\nRoll No: %d\n", s[i].rollNo);
        printf("Name   : %s\n", s[i].name);
        printf("Total  : %d\n", s[i].total);
        printf("Average: %.2f\n", s[i].average);

        if (s[i].average >= 50)
            printf("Result : PASS\n");
        else
            printf("Result : FAIL\n");
    }

    return 0;
}
