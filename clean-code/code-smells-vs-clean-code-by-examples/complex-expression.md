# Complex expression

#### Code smell

{% tabs %}
{% tab title="Java" %}
```java
void renderBanner() {
  if ((platform.toUpperCase().indexOf("MAC") > -1) &&
       (browser.toUpperCase().indexOf("IE") > -1) &&
        wasInitialized() && resize > 0 )
  {
    // do something
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
void renderBanner() {
  final boolean isMacOs = platform.toUpperCase().indexOf("MAC") > -1;
  final boolean isIE = browser.toUpperCase().indexOf("IE") > -1;
  final boolean wasResized = resize > 0;

  if (isMacOs && isIE && wasInitialized() && wasResized) {
    // do something
  }
}
```
{% endtab %}

{% tab title="TypeScript" %}

{% endtab %}
{% endtabs %}

{% hint style="danger" %}
Short-circuit evaluation is not applied in the case of refactored method, therefore it will take more time to finish the execution
{% endhint %}

{% hint style="info" %}
Developer costs will be increased by the time but computer power will become cheaper and cheaper so it's not worth worrying about a small loss of performance
{% endhint %}

{% hint style="warning" %}
The modern compiler could apply the short-circuit evaluation in the case of refactored method? If it's not the case, extract complex conditional expressions to new methods&#x20;
{% endhint %}
