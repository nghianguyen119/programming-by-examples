# 🤽♀ Hide Delegate

#### Code smell

<figure><img src="https://refactoring.guru/images/refactoring/diagrams/Hide%20Delegate%20-%20Before.png" alt=""><figcaption></figcaption></figure>

{% tabs %}
{% tab title="Java" %}
```java
class Person {
    private Department workDepartment;
    public Department getWorkDepartment(){
        return workDepartment;
    }
}

class Department {
    private Employee manager;
    public Employee getManager(){
        return manager;
    }
}

class Client {
    public void test(){
	Person john = new Person();
	Department johnDepartment = john.getWorkDepartment();
	Person johnManager = johnDepartment.getManager();
    }
}
```
{% endtab %}
{% endtabs %}

<figure><img src="https://refactoring.guru/images/refactoring/diagrams/Hide%20Delegate%20-%20After.png" alt=""><figcaption></figcaption></figure>

{% tabs %}
{% tab title="Java" %}
```java
class Person {
    private Department workDepartment;
    public Person getManager(){
	return workDepartment.getManager()
    }
}

class Department {
    private Person manager;
    public Person getManager() {
	return manager;
    }
}

class Client {
    public void test(){
	Person john = new Person();
	Person johnManager = john.getManager();
    }
}
```
{% endtab %}

{% tab title="TypeScript" %}

{% endtab %}
{% endtabs %}

{% hint style="info" %}

{% endhint %}
