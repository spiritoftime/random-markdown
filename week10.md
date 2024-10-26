### Issue: Why does the code keep crashing whenever I perform operation 2 - Add a DVD?

```java
    public void start() {
        int choice;
        do {
            // question: why does this line below make the whole code hang when running??
            // // flush the previous choice, because you end up with .NoSuchElementException
            // // after performing an operation that is not 5.
            // sc.nextLine();
            display();
            choice = sc.nextInt();
            System.out.println("Choice inputted was " + choice);
            switch (choice) {
                case 1:
                    processListAllDVDs();
                    break;
                case 2:
                    // why dont i reuse scanner here?
                    processAddDVD();
                    break;
                case 3:
                    processRentDVD();
                    break;
                case 4:
                    processListAllRentals();
                    break;
                case 5:
                    System.out.println("bye bye");
                    break;
                default:
                    System.out.println("Enter a choice between 1 to 5 ");
            }
        } while (choice != 5);
        sc.close();
    }
```
### Stack Trace:
```java
Liang Wei@DESKTOP-1FQBNLB MINGW64 ~/Downloads/ICE10-exception2-resource/ICE10-exception2-resource/q5
$  cd c:\\Users\\Liang\ Wei\\Downloads\\ICE10-exception2-resource\\ICE10-exception2-resource\\q5 ; /usr/bin/env C:\\Users\\Liang\ Wei\\AppData\\Local\\Programs\\Eclipse\ Adoptium\\jdk-17.0.11.9-hotspot\\bin\\java.exe -XX:+ShowCodeDetailsInExceptionMessages -cp C:\\Users\\Liang\ Wei\\AppData\\Roaming\\Code\\User\\workspaceStorage\\c6f18415e06c9da21d26826c96a37a3d\\redhat.java\\jdt_ws\\q5_394fbd2\\bin RentalApplication
== DVD Rental ==
1. List all DVDs
2. Add a DVD
3. Rent a DVD
4. List all rentals
5. Quit Application

Please enter your choice:2
Choice inputted was 2

== DVD Rental::Add DVD ==
Enter the title > title
Title inputted was title
adding title
new title id is 6
DVD added successfully!

== DVD Rental ==
1. List all DVDs
2. Add a DVD
3. Rent a DVD
4. List all rentals
5. Quit Application

Please enter your choice:Exception in thread "main" java.util.NoSuchElementException
        at java.base/java.util.Scanner.throwFor(Scanner.java:937)
        at java.base/java.util.Scanner.next(Scanner.java:1594)
        at java.base/java.util.Scanner.nextInt(Scanner.java:2258)
        at java.base/java.util.Scanner.nextInt(Scanner.java:2212)
        at RentalMenu.start(RentalMenu.java:56)
        at RentalApplication.main(RentalApplication.java:6)
```


### What I tried:
1. tried to reuse the scanner from RentalMenu constructor
```java
   case 2:
  // why dont i reuse scanner here?
  processAddDVD();
  break;
```
2. tried to flush the choice with sc.nextLine(); after performing 2. the whole code just hangs and I ended down a deep rabbit hole of looking at java runtime versions to no avail. https://stackoverflow.com/questions/47457105/class-has-been-compiled-by-a-more-recent-version-of-the-java-environment
```java
  do {
      // question: why does this line below make the whole code hang when running??
      // // flush the previous choice, because you end up with .NoSuchElementException
      // // after performing an operation that is not 5.
      // sc.nextLine();
      display();
```
![image](https://github.com/user-attachments/assets/74f8dfec-8945-4ce4-9bd9-d5f0cb411f4f)
