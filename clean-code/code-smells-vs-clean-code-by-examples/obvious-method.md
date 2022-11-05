# Obvious method

#### Code smell

{% tabs %}
{% tab title="Java" %}
<pre class="language-java"><code class="lang-java">public static String logKeyValuePairs(String... strings) {
    String serializedkeyValues = "";
<strong>    for (int i = 0; i &#x3C; strings.length; i++)
</strong>        serializedkeyValues += isEven(i) ? strings[i] + ": " : strings[i] + "\n";
    return serializedkeyValues;
}

private static boolean isEven(int i){
    return (i % 2) == 0;
}</code></pre>
{% endtab %}

{% tab title="TypeScript" %}

{% endtab %}
{% endtabs %}

#### Refactored code

{% tabs %}
{% tab title="Java" %}
<pre class="language-java"><code class="lang-java">public static String logKeyValuePairs(String... strings) {
    String serializedkeyValues = "";
<strong>    for (int i = 0; i &#x3C; strings.length; i++)
</strong>        serializedkeyValues += (i % 2) == 0 ? strings[i] + ": " : strings[i] + "\n";
    return serializedkeyValues;
}</code></pre>
{% endtab %}

{% tab title="TypeScript" %}

{% endtab %}
{% endtabs %}

{% hint style="danger" %}
This example could be controversial. In general, it's recommended to avoid the methods that have the method body more obvious than the method itself. E.g. isPositive(int i), isNegative(int i), moreThanFiveFaillures(int nbrOfFaillure) are not necessary
{% endhint %}
