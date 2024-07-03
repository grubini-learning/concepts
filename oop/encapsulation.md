# Encapsulation

- protect members of the class and some methods from external

## Principles

- create constructors for object init, which enforces logic
- use private access modifier for fields
- use setter methods sparingly and as needed
- use methods that aren't private, only for calling code needs to use

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

    private void drawLogo() {
        monitor.drawPixelAt(1200, 50, "yellow");
    }

    public void powerUp() {
        computerCase.pressPowerButton();
        drawLogo();
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
