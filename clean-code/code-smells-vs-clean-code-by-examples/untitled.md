# Untitled

#### Code smell

{% tabs %}
{% tab title="Java" %}
```java
int discount(int inputVal, int quantity) {
  if (quantity > 50) {
    inputVal -= 2;
  }
  return inputVal;
}
```
{% endtab %}

{% tab title="TypeScript" %}

{% endtab %}
{% endtabs %}

#### Refactored code

{% tabs %}
{% tab title="Java" %}
<pre class="language-java"><code class="lang-java">int discount(int inputVal, int quantity) {
  int result = inputVal;
  if (quantity > 50) {
<strong>    result -= 2;
</strong>  }
  return result;
}</code></pre>
{% endtab %}

{% tab title="TypeScript" %}

{% endtab %}
{% endtabs %}

{% hint style="info" %}
Each element of the program should be responsible for only one thing
{% endhint %}
