---
description: >-
  Long method would create duplication of codes, too many local variable, hard
  to maintain, hard to understand
---

# Long Method

{% tabs %}
{% tab title="First Tab" %}
```java
void printOwing() {
  printBanner();

  // Print details.
  System.out.println("name: " + name);
  System.out.println("amount: " + getOutstanding());va
```
{% endtab %}

{% tab title="Second Tab" %}
```java
void printOwing() {
  printBanner();

  // Print details.
  System.out.println("name: " + name);
  System.out.println("amount: " + getOutstanding());
```
{% endtab %}
{% endtabs %}

{% code title="" overflow="wrap" %}
```java
void printOwing() {
  printBanner();
  System.out.println("name: " + name);
  System.out.println("amount: " + getOutstanding());
}
```
{% endcode %}

{% hint style="success" %}
If you feel the need to comment on something inside a method, take this code and put it in a new method
{% endhint %}

{% hint style="success" %}
Even a single line can and should be split off into a separate method
{% endhint %}

