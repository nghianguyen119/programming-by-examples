# Replace Temporary with Query

#### Code smell

{% tabs %}
{% tab title="Java" %}
```java
double calculateTotal() {
  double basePrice = quantity * itemPrice;
  if (basePrice > 1000) {
    return basePrice * 0.95;
  }
  else {
    return basePrice * 0.98;
  }
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
double calculateTotal() {
  if (basePrice() > 1000) {
    return basePrice() * 0.95;
  }
  else {
    return basePrice() * 0.98;
  }
}

double basePrice() {
  return quantity * itemPrice;
}
```
{% endtab %}

{% tab title="TypeScript" %}

{% endtab %}
{% endtabs %}

{% hint style="info" %}
This refactoring increases readability but lowers performance. If the extracted method is time-consuming, it's recommended to avoid it.
{% endhint %}
