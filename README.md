## Question PDF Link : 
**Answer all 4 (Four) questions.**

| Q | | Question | Marks | Level | CLO |
|---|---|----------|:-----:|-------|-----|
| **1.** | a) | Define *software design*. What is the input of the design process? List the two basic steps of the design process and state what each describes. | 4 | Remember | CLO1 |
| | b) | Define *coupling* and *cohesion*. Which one should be low and which one should be high in a good design? | 3 | Remember | CLO1 |
| | c) | Explain why recording the rationale of design decisions improves the maintainability of software. | 3 | Understand | CLO1 |
| **2.** | a) | Explain how the Model-View-Controller (MVC) style separates responsibilities. Describe the role of Model, View and Controller. | 4 | Understand | CLO3 |
| | b) | Distinguish between *Page Controller* and *Front Controller*. In which kind of website is each one suitable? | 3 | Understand | CLO3 |
| | c) | Name the three categories of GoF design patterns and give one example of each. | 3 | Remember | CLO4 |
| **3.** | a) | Compute **LCOM** (show sets P and Q) and **LCOM2** for the `Book` class given below. Comment on its cohesion. | 6 | Apply | CLO2 |
| | b) | Compute **CBO** and the McCabe version of **WMC** for the `OrderService` class given below (count only project classes). | 4 | Apply | CLO2 |
| **4.** | a) | An online shop supports Card, bKash and PayPal payment, chosen at runtime. The `Checkout` class currently uses a long if-else chain. Name the GoF pattern that solves this, map its roles to the classes in this scenario with a class diagram, and state one benefit and one liability. | 6 | Apply | CLO4 |
| | b) | Explain any three UI design principles with one example each. | 4 | Understand | CLO5 |

**Code for Q3(a):**

```java
public class Book {
    private String title, author;
    private int copies;
    public String getTitle()     { return title; }
    public String getAuthor()    { return author; }
    public void addCopies(int n) { copies += n; }
    public boolean isAvailable() { return copies > 0; }
}
```

**Code for Q3(b):**

```java
class OrderService {
    private Printer printer;
    private Mailer mailer;
    public void place(Order o) {
        if (o == null) return;
        if (o.isPaid()) { mailer.send(o); printer.print(o); }
        else System.out.println("Unpaid");
    }
    public void cancel(Order o) {
        if (o != null) mailer.send(o);
    }
}
```
