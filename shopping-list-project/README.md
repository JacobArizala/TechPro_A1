# 🛒 Shopping List Project

**Name:** Christian Jacob Arizala  
**Program Title:** Shopping List Program  

--- Description ---
The user of this Java application can make a simple shopping list that includes the addition of five items at most, 
the showing of all items added, 
the counting of total items, 
and a search option to find out if a 
certain item is on the list.
---

## 🧪 Sample Input
import java.util.ArrayList;
import java.util.Scanner;

public class ShoppingList {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        ArrayList<String> shoppingList = new ArrayList<>();
        int maxItems = 5;
        System.out.println("Enter up to 5 items to buy:");
        while (shoppingList.size() < maxItems) {
            System.out.print("Item " + (shoppingList.size() + 1) + ": ");
            String item = scanner.nextLine();

            if (!item.isEmpty()) {
                shoppingList.add(item);
            } else {
                System.out.println("Item cannot be empty. Try again.");
            }
        }
        System.out.println("\nYour shopping list:");
        for (int i = 0; i < shoppingList.size(); i++) {
            System.out.println("- " + shoppingList.get(i));
        }
        System.out.println("You entered " + shoppingList.size() + " items.");
        System.out.print("\nSearch for an item: ");
        String searchItem = scanner.nextLine().toLowerCase();

        boolean found = false;
        for (String item : shoppingList) {
            if (item.toLowerCase().equals(searchItem)) {
                found = true;
                break;
            }
        }

        if (found) {
            System.out.println(searchItem + " is in your shopping list!");
        } else {
            System.out.println(searchItem + " is NOT in your shopping list.");
        }

        scanner.close();
    }
}


OUTPUT
Enter up to 5 items to buy:
Item 1: milk
Item 2: eggs
Item 3: rice
Item 4: soap
Item 5: coffee

Your shopping list:
milk, eggs, rice, soap, coffee

You entered 5 items.

Search for an item: rice
✅ rice is in your shopping list!

