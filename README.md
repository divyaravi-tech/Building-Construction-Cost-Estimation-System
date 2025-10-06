# Building-Construction-Cost-Estimation-System
This project estimates the total construction cost of a building.
#include <stdio.h>

int main() {
    int floors;
    float area, totalArea, totalCost;
    int materialType, automation;

    printf("---- BUILDING CONSTRUCTION COST ESTIMATION ----\n");

    printf("Enter number of floors: ");
    scanf("%d", &floors);

    printf("Enter area of one floor (in square feet): ");
    scanf("%f", &area);

    totalArea = floors * area;

    printf("\nChoose Material Type:\n");
    printf("1. Standard Material (₹1200 per sq.ft)\n");
    printf("2. Above Standard Material (₹1500 per sq.ft)\n");
    printf("3. High Standard Material (₹1800 per sq.ft)\n");
    printf("Enter your choice: ");
    scanf("%d", &materialType);

    printf("Do you want full automation? (1 = Yes, 0 = No): ");
    scanf("%d", &automation);

    switch (materialType) {
        case 1:
            totalCost = totalArea * 1200;
            break;
        case 2:
            totalCost = totalArea * 1500;
            break;
        case 3:
            if (automation == 1)
                totalCost = totalArea * 2500;  // automated high standard
            else
                totalCost = totalArea * 1800;  // manual high standard
            break;
        default:
            printf("Invalid material type!\n");
            return 0;
    }

    printf("\n---- ESTIMATION REPORT ----\n");
    printf("Total Area: %.2f sq.ft\n", totalArea);
    printf("Material Type: %s\n", 
           (materialType == 1) ? "Standard" :
           (materialType == 2) ? "Above Standard" : "High Standard");
    printf("Automation: %s\n", automation ? "Yes" : "No");
    printf("Estimated Construction Cost: ₹%.2f\n", totalCost);

    return 0;
}
