# Inner class

```java
class Outer {
    public void aNormalClassHere() {
    }

    class Inner { // Outer$Inner.class; it could be static also
	public void anInnerFoo() {
	}
    }
}

public class Learn {
    public static void main(String[] args) {
	Outer objOuter = new Outer();
	Outer.Inner objInner = objOuter.new Inner();
	// Outer.Inner objInner = new Outer.Inner(); if Inner is static
	objInner.anInnerFoo();
    }
}

```
