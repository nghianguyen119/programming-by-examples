# Try with ressource

{% tabs %}
{% tab title="Without auto close ressource" %}
```java
public class Learn {
    public static void main(String[] args) throws IOException {
	System.out.println("Enter a number");
	BufferedReader buffer = null;
	try {
	    buffer = new BufferedReader(new InputStreamReader(System.in));
	    System.out.println(Integer.parseInt(buffer.readLine()));
	} finally {
	    buffer.close();
	}
    }
}
```
{% endtab %}

{% tab title="Auto close ressource" %}
```java
public class Learn {
    public static void main(String[] args) throws IOException {
	System.out.println("Enter a number");
	try (BufferedReader buffer = new BufferedReader(new InputStreamReader(System.in))) {
	    System.out.println(Integer.parseInt(buffer.readLine()));
	}
    }
}
```
{% endtab %}
{% endtabs %}
