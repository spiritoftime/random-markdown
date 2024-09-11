Hello Prof Ivan,


(1)I'm still confused on why for qn12, part a is wrong
![image](https://github.com/user-attachments/assets/2f7f7f82-8d86-479a-bb58-504855e5f6ef)


(2) This week's ICE, qn1 - I was wondering if there is a better way to safeguard against test cases not passing the correct argument. For example:
```
  public static ArrayList<Shape> getAllNonRectangles(ArrayList<Shape> shapeList) {
    // if there is no list
    if (shapeList == null) {
      return null;
    }
    ArrayList<Shape> nonRectangles = new ArrayList<Shape>();
    for (Shape s : shapeList) {
      if (!(s instanceof Rectangle)) {
        nonRectangles.add(s);
      }
    }
    return nonRectangles;
  }
```
ShapeUtilityTest.java:
```
    System.out.println(ShapeUtility.getAllNonRectangles(null));
```
If future test cases pass in int or something, would there be a better way of safeguarding against these edge cases, other than copy pasting the same check for all functions?

(3) Qn 2 ICE this week - just wanna check if there is a difference between super.setValue, and this.setValue.
```
public class CircularCounter extends Counter {
  private int limit;

  public CircularCounter(int limit) {
    super(0);
    this.limit = limit;
  }

  @Override
  public void decrement() {
    if (this.getValue() == 0) {
      super.setValue(limit);
      // VS
      // this.setValue(limit);
    } else {
      super.decrement();
    }
  }

  @Override
  public void increment() {
    if (this.getValue() == this.limit) {
      super.setValue(0);
    } else {
      super.increment();
    }
  }
}

```

(4) So yesterday prof Jason taught us that to test our code against the test cases, we need to run javac *.java, then java ShapeUtilityTest.java for example. 
He also sugggested we cd into each question's respective folders. However for Q3, Im struggling to run the code, because Shape.class and all those cannot be found.
![image](https://github.com/user-attachments/assets/0e61d18d-b531-4c85-95dc-fdfdee086691)

Even if i cd out to have its files, I'm still struggling to run the code:
![image](https://github.com/user-attachments/assets/ed8400b5-8bc4-43a0-b2ec-14b302403699)
