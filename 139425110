#include <stdio.h>
#include <string.h>

#define MAX 100

typedef struct
{
    char type[10];
    float amount;
} Transaction;

int main(void)
{
    Transaction list[MAX];
    int count = 0;

    float balance = 0.0;
    int running = 1;

    printf("=== Checkbook Balancer ===\n");
    printf("Enter starting balance: ");
    scanf("%f", &balance);

    while (running)
    {
        int choice;
        printf("\n---- MENU ----\n");
        printf("1. Deposit\n");
        printf("2. Withdraw\n");
        printf("3. Show Balance\n");
        printf("4. Show Transactions\n");
        printf("5. Exit\n");
        printf("Choose: ");
        scanf("%d", &choice);

        if (choice == 1)
        {
            float amount;
            printf("Deposit amount: ");
            scanf("%f", &amount);

            if (amount <= 0)
            {
                printf("Invalid amount.\n");
            }
            else if (count < MAX)
            {
                strcpy(list[count].type, "deposit");
                list[count].amount = amount;
                balance += amount;
                count++;
                printf("Deposited.\n");
            }
        }
        else if (choice == 2)
        {
            float amount;
            printf("Withdraw amount: ");
            scanf("%f", &amount);

            if (amount <= 0)
            {
                printf("Invalid amount.\n");
            }
            else if (amount > balance)
            {
                printf("Not enough funds.\n");
            }
            else if (count < MAX)
            {
                strcpy(list[count].type, "withdraw");
                list[count].amount = amount;
                balance -= amount;
                count++;
                printf("Withdrawn.\n");
            }
        }
        else if (choice == 3)
        {
            printf("Current balance: %.2f\n", balance);
        }
        else if (choice == 4)
        {
            if (count == 0)
            {
                printf("No transactions yet.\n");
            }
            else
            {
                printf("\n--- TRANSACTION HISTORY ---\n");
                for (int i = 0; i < count; i++)
                {
                    printf("%d. %s: %.2f\n", i + 1, list[i].type, list[i].amount);
                }
            }
        }
        else if (choice == 5)
        {
            running = 0;
        }
        else
        {
            printf("Invalid option.\n");
        }
    }

    printf("Goodbye.\n");
    return 0;
}
