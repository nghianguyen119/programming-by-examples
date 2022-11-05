# Multiple class in a file&#x20;

```java
public class Main {
    public static void main(String[] args){
	Hello.printSt();
    }
}

class Hello {
    public static void printSt(){
	System.out.println("Hello");
    }
}
```

{% hint style="info" %}
The modifier of Hello class is "package-private", can't change to public
{% endhint %}
