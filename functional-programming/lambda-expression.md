# Lambda Expression

In Java 8 and above, lambda expression is a short way to implement the functional interface

{% tabs %}
{% tab title="Before Java 8" %}
<pre class="language-java"><code class="lang-java"><strong>// There are two ways to implement functional interface before java8
</strong><strong>// Either classic way or using anonymous class
</strong><strong>
</strong><strong>@FunctionalInterface
</strong>interface A {
    void soleFunction();
}

class B implements A {
    @Override
    public void soleFunction() {
	System.out.println("Do something");
    }
}

public class Learn {
    public static void main(String[] args) {
	A obj = new A() {
	    public void soleFunction() {
		System.out.println("Do something");
	    }
	};
	obj.soleFunction();
	
	B way_2 = new B();
	way_2.soleFunction();
    }
}</code></pre>
{% endtab %}

{% tab title="Java >= 8" %}
```java
// forEach, map, filter, other functions in stream actually require
// the object that implement functional interface

@FunctionalInterface
interface A {
    void soleFunction();
}

public class Learn {
    public static void main(String[] args) {
	A obj = () -> System.out.println("Do something");
	obj.soleFunction();
    }
}

```
{% endtab %}
{% endtabs %}
