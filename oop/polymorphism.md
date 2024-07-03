# Polymorphism

Different forms. For it to work the declared type must have a relationship with the runtime type.
Inheritance is one way to establish this relationship

```java
public class Movie {
    private String title;

    public Movie(String title) {
        this.title = title;
    }

    public void watchMovie() {
        String instanceType = this.getClass().getSimpleName();
        System.out.print(title + " is a " + instanceType + " film");
    }
}

class Adventure extends Movie {
    public Adventure(String title) {
        super(title);
    }

    @Override
    public void watchMovie() {
        super.watchMovie();
        System.out.printf("..%s%n".repeat(3), "Pleasant scene", "Scary Music", "Something Bad Happens");
    }
}
class Comedy extends Movie {
    public Comedy(String title) {
        super(title);
    }

    @Override
    public void watchMovie() {
        super.watchMovie();
        System.out.printf("..%s%n".repeat(3), "Something funny", "Something funnier", "Happy Ending");
    }
}
```

## Patterns

### Factory

Methods that gives an object without having to know the details of how to create one
