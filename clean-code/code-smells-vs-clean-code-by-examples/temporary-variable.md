# Temporary variable

#### Code smell

{% tabs %}
{% tab title="Java" %}
```java
boolean hasDiscount(Order order) {
  double basePrice = order.basePrice();
  return basePrice > 1000;
}
```
{% endtab %}

{% tab title="TypeScript" %}

{% endtab %}
{% endtabs %}

#### Refactored code

{% tabs %}
{% tab title="Java" %}
```java
boolean hasDiscount(Order order) {
  return order.basePrice() > 1000;
}
```
{% endtab %}

{% tab title="TypeScript" %}

{% endtab %}
{% endtabs %}
