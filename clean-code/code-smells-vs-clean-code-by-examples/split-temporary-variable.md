# Split Temporary Variable

#### Code smell

{% tabs %}
{% tab title="Java" %}
```java
double temp = 2 * (height + width);
System.out.println(temp);
temp = height * width;
System.out.println(temp);
```
{% endtab %}

{% tab title="TypeScript" %}

{% endtab %}
{% endtabs %}

#### Refactored code

{% tabs %}
{% tab title="Java" %}
```java
final double perimeter = 2 * (height + width);
System.out.println(perimeter);
final double area = height * width;
System.out.println(area);
```
{% endtab %}

{% tab title="TypeScript" %}

{% endtab %}
{% endtabs %}

{% hint style="info" %}
Use different variables for different purposes
{% endhint %}
