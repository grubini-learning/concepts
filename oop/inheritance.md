# Inheritance

Defines a IS A relationship

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
    public PersonalComputer(String model, String manufacturer) {
        super(model, manufacturer);
    }
}
public class Monitor extends Product {
    public Monitor(String model, String manufacturer) {
        super(model, manufacturer);
    }
}
public class Motherboard extends Product {
    public Motherboard(String model, String manufacturer) {
        super(model, manufacturer);
    }
}
public class ComputerCase extends Product {
    public ComputerCase(String model, String manufacturer) {
        super(model, manufacturer);
    }
}
```
