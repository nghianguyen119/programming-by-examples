# Inspiration

### Example 1

<pre class="language-java"><code class="lang-java">// Given
final List&#x3C;BigDecimal> prices = Arrays.asList(
<strong>    new BigDecimal("10"), new BigDecimal("30"), new BigDecimal("17"),
</strong>    new BigDecimal("20"), new BigDecimal("15"), new BigDecimal("18"),
    new BigDecimal("45"), new BigDecimal("12"));</code></pre>

Demand: total the prices greater than $20

#### Imperative solution

```java
BigDecimal totalOfDiscountedPrices = BigDecimal.ZERO;
for(BigDecimal price : prices) {
    if(price.compareTo(BigDecimal.valueOf(20)) > 0)
        totalOfDiscountedPrices =
            totalOfDiscountedPrices.add(price.multiply(BigDecimal.valueOf(0.9)));
}
System.out.println("Total of discounted prices: " + totalOfDiscountedPrices);
```

#### Declarative solution

```java
final BigDecimal totalOfDiscountedPrices =
    prices.stream()
        .filter(price -> price.compareTo(BigDecimal.valueOf(20)) > 0)
        .map(price -> price.multiply(BigDecimal.valueOf(0.9)))
        .reduce(BigDecimal.ZERO, BigDecimal::add);
System.out.println("Total of discounted prices: " + totalOfDiscountedPrices);
```

{% hint style="info" %}
There would not be multiple loops in the declarative solution as it looks like, performace is guaranteed
{% endhint %}
