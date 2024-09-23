Lab Test Part 1:
Q4 - can I check why it is not 0..1 for both LinkedList and reflexive at Node?


![image](https://github.com/user-attachments/assets/56925a38-8722-4005-a9cb-e1b8fb5062fc)

Lab Test part 2

Q2: For me, I thought the way of revival was via takeTreatment; the patient will automatically revive as long as takeTreatment got patient back to at least 1 health. I didnt think of using constructor to revive. Is constructor to revive better?
```java
public class CriticalPatient extends Patient {
    // instance variables
    protected int numDeaths = 0;

    // constructor
    public CriticalPatient(int health) {
        super(health);
    }

    // instance method
    public void deteriorateHealth() {
        // once health hits 0, you cant decrease health anymore.
        // you are already dead.
        if (this.health >= 1) {
            this.health -= 1;
            if (this.health == 0) {
                numDeaths += 1;
            }
        }

    }

    public boolean isPatientDead() {
        return this.health <= 0;
    }

    // overridden instance method
    @Override
    public void takeTreatment() {
        this.health += 2;
    }

    public int getNumDeaths() {
        return this.numDeaths;
    }
}

```


Q3: Is there any penalty if I use iterator to iterate/ if i use hashmap for uniqueSize()?
```java
import java.util.HashMap;

public class SortedLinkedList {

    // Instance variables

    // The node at the start of the list
    private Node head;

    // constructor
    public SortedLinkedList() {
    }

    // Instance methods

    public void add(int element) {
        Node newEle = new Node(element);

        // if linked list has nothing yet
        if (this.head == null) {
            this.head = newEle;
            return;
        }
        int i = 0;
        Node curr = head;
        Node prev = null;
        // while it is less, go next until it reaches tail.
        while (curr.getValue() < element && curr.getNext() != null) {
            prev = curr;
            curr = curr.getNext();
        }

        // case 2 - newEle > curr. eg: [3,5] add 6.

        if (curr.getValue() < element) {
            curr.setNext(newEle);
        } else {
            // case 1 - newEle < curr. eg: [5] add 3
            // case 1.1 - need update head
            // case 1.2 - [3,5] add 4
            if (this.head.getValue() > element) {
                newEle.setNext(this.head);
                this.head = newEle;

            } else {
                prev.setNext(newEle);
                newEle.setNext(curr);
            }

        }
    }

    public boolean remove(int element) {
        Node prev = head;
        Node curr = head;
        // while it is less, go next
        while (curr.getValue() < element) {
            prev = curr;
            curr = curr.getNext();
        }
        // couldnt find the element
        if (curr.getValue() != element)
            return false;
        // if found element
        Node next = curr.getNext();
        prev.setNext(next);
        return true;
    }

    public int get(int position) {

        // Start at first node (head)
        int i = 0;
        Node current = head;

        // Keep going until we reach target position
        while (i < position) {

            // Keep asking for the next node, and increment counter
            current = current.getNext();
            i++;
        }

        // Return value at this node
        return current.getValue();
    }

    public int size() {

        // Start at first node (head)
        int i = 0;
        Node current = head;

        // Keep going until current node does not exist
        while (current != null) {

            // Keep asking for the next node, and increment counter
            current = current.getNext();
            i++;
        }

        // Return count
        return i;
    }

    public int uniqueSize() {
        HashMap<Integer, Boolean> hm = new HashMap<Integer, Boolean>();
        // Start at first node (head)
        Node current = head;

        // Keep going until current node does not exist
        while (current != null) {
            hm.put(current.getValue(), true);
            // Keep asking for the next node, and increment counter
            current = current.getNext();
        }
        return hm.keySet().size();
    }
}
```
