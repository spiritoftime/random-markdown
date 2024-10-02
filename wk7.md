1. Can I check what is the difference between list and Array? Q3 of ICE:
My code:
 ```java
import java.util.ArrayList;
import java.util.Map;

public class ItemTool {
  public static InventoryItem[] getAllInventoryItemsLighterThan(InventoryItem[] items, double weight) {
    ArrayList<InventoryItem> finalList = new ArrayList<InventoryItem>();
    for (InventoryItem i : items) {
      if (i.getWeight() < weight) {
        finalList.add(i);
      }
    }
    // put it in a fixed size list
    InventoryItem[] returnLs = new InventoryItem[finalList.size()];
    int idx = 0;
    for (InventoryItem i : finalList) {

      returnLs[idx] = i;
      idx++;
    }
    return returnLs;
  }

  public static Magazine[] getAllMagazines(InventoryItem[] items) {
  }

  public static InventoryItem[] getAllNonBooksOfCategory(InventoryItem[] items, char category) {
  }

  public static Laptop[] getAllLaptopsWithNumCpuGreaterThan(Map<String, InventoryItem> map, int numCpu) {
  }
}
```

![image](https://github.com/user-attachments/assets/b9882e1e-9773-4322-a4c9-9b5e71906f7a)

Tried using List
```java
import java.util.ArrayList;

public class ItemTool {
  public static List<InventoryItem> getAllInventoryItemsLighterThan(List<InventoryItem> items, double weight) {
    ArrayList<InventoryItem> finalList = new ArrayList<InventoryItem>();
    for (InventoryItem i : items) {
      if (i.getWeight() < weight) {
        finalList.add(i);
      }
    }
    // put it in a fixed size list
    InventoryItem[] returnLs = new InventoryItem[finalList.size()];
    int idx = 0;
    for (InventoryItem i : finalList) {

      returnLs[idx] = i;
      idx++;
    }
    return returnLs;
  }

  public static List<Magazine> getAllMagazines(List<InventoryItem> items) {
  }

  public static List<InventoryItem> getAllNonBooksOfCategory(List<InventoryItem> items, char category) {
  }

  public static List<Laptop> getAllLaptopsWithNumCpuGreaterThan(Map<String, InventoryItem> map, int numCpu) {
  }
}
```

ended up with ![image](https://github.com/user-attachments/assets/3d6a9fc3-b6eb-491e-813b-f666fd76418d)

