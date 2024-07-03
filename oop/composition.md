# Composition

A way to make the combination of classes act like a single coherent object. Defines HAS A relationship

## Composition over Inheritance

- Composition is more flexible than inheritance because you can add parts or remove them, and these changes are less likely to cascade.
- Provides functional reuse outside of the class hierarchy, meaning classes can share attributes & behaviors, by having similar components.
- Java inheritance breaks encapsulation because subclasses may need direct access to parent's state behavior.

-- When designing programs in Java, we want to look at composition first.

```java
public class Product {
    private String model;
    private String manufacturer;
    private int width;
    private int height;


    public Product(String model, String manufacturer) {
        this.model = model;
        this.manufacturer = manufacturer;
    }
}

public class PersonalComputer extends Product {
    private Monitor monitor;
    private Motherboard motherboard;
    private ComputerCase computerCase;

    public PersonalComputer(String model, String manufacturer) {
        super(model, manufacturer);
    }

    public PersonalComputer(String model, String manufacturer, Monitor monitor, Motherboard motherboard, ComputerCase computerCase) {
        super(model, manufacturer);

        this.monitor = monitor;
        this.motherboard = motherboard;
        this.computerCase = computerCase;
    }

    public Monitor getMonitor() {
        return this.monitor;
    }

    public Motherboard getMotherboard() {
        return this.motherboard;
    }

    public ComputerCase getComputerCase() {
        return this.computerCase;
    }
}

public class Monitor extends Product {
    private int size;
    private String resolution;

    public Monitor(String model, String manufacturer) {
        super(model, manufacturer);
    }

    public Monitor(String model, String manufacturer, int size, String resolution) {
        super(model, manufacturer);

        this.size = size;
        this.resolution = resolution;
    }

    public void drawPixelAt(int x, int y, String color) {}
}

public class Motherboard extends Product {
    private int ramSlots;
    private int cardSlots;
    private String bios;

    public Motherboard(String model, String manufacturer) {
        super(model, manufacturer);
    }

    public MotherBoard(String model, String manufacturer, int ramSlots, int cardSlots, String bios) {
        super(model, manufacturer);

        this.ramSlots = ramSlots;
        this.cardSlots = cardSlots;
        this.bios = bios;
    }

    public void loadProgram(String programName) {}
}

public class ComputerCase extends Product {
    private String powerSupply;

    public ComputerCase(String model, String manufacturer) {
        super(model, manufacturer);
    }

    public ComputerCase(String model, String manufacturer, String powerSupply) {
        super(model, manufacturer);

        this.powerSupply = powerSupply;
    }

    public void pressPowerButton() {}
}
```

```java
ComputerCase theCase = new ComputerCase("208", "Dell", "240");
Monitor theMonitor = new Monitor("32inch WideScreen", "LG", "3240 X 3100");
Motherboard theMotherboard = new Motherboard("Z790-A WIFI", "Asus", "12", "4", "UEFI");

PersonalComputer thePC = new PersonalComputer("2208", "Dell", theMonitor, theMotherboard, theCase);
thePC.getMonitor().drawPixelAt(20, 10, "red");
thePC.getMotherboard().loadProgram("Mac OS");
thePC.getComputerCase().pressPowerButton();
```
