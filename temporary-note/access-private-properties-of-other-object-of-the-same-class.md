# Access private properties of other object of the same class



```java
public class Point {
    private int x;

    public void modifier(Point p) {
	this.x = p.x; // works
    }
}
```

