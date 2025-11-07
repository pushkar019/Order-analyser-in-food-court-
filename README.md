# Order-analyser-in-food-court-
#include <stdio.h>

struct food {
    int food_number;
    char food_name[50];
    float food_price;
};

int main() {
     int i, j,f;
    printf("enter no.of dish:\n");
    scanf("%d",&f);
    struct food si[f];
   
    struct food temp_food; 
    int n = f;             

   
    printf("\n--- Enter Food Dish Details ---\n");
    for (i = 0; i < n; i++) {
        printf("\n--- Dish %d ---\n", i + 1);
        printf("Enter dish number: ");
        scanf("%d", &si[i].food_number);
        printf("Enter dish name: ");
        
        scanf("%s", si[i].food_name);
        printf("Enter price of dish: ");
        scanf("%f", &si[i].food_price);
    }

   
    for (i = 0; i < n - 1; i++) {
        
        for (j = 0; j < n - i - 1; j++) {
            
            
            if (si[j].food_price > si[j + 1].food_price) {
                
               
                temp_food = si[j];
                si[j] = si[j + 1];
                si[j + 1] = temp_food;
            }
        }
    }

    
    printf("\n--- Menu Sorted by Price (Ascending) ---\n");
    printf("%-10s %-20s %s\n", "Number", "Name", "Price");
    printf("-------------------------------------------\n");
    for (i = 0; i < n; i++) {
        printf("%-10d %-20s $%.2f\n", 
               si[i].food_number, si[i].food_name, si[i].food_price);
    }

    return 0;
}


