# 🤽♀ Remove Middle Man (Reverse of Hide Delegate)

#### Code smell

<figure><img src="https://refactoring.guru/images/refactoring/diagrams/Hide%20Delegate%20-%20After.png" alt=""><figcaption></figcaption></figure>

{% tabs %}
{% tab title="Java" %}
```java
class Person {
    private Department workDepartment;
    public Person getManager(){
	return workDepartment.getManager()
    }
    public String getWorkAddress(){
        return workDepartment.getAddress();
    }
}

class Department {
    private Person manager;
    public Person getManager() {
	return manager;
    }
    
    private String address;
    public String getAddress(){
        return address;
    }
}

class Client {
    public void test(){
	Person john = new Person();
	Person johnManager = john.getManager();
	String johnWorkAddress = john.getWorkAddress();
    }
}
```
{% endtab %}
{% endtabs %}

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
    
    private String address;
    public String getAddress(){
        return address;
    }
}

class Client {
    public void test(){
	Person john = new Person();
	Department johnDepartment = john.getWorkDepartment();
	Person johnManager = johnDepartment.getManager();
	String johnWorkAddress = johnDepartment.getAddress();
    }
}
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
Use this refactoring when Deparment has many props
{% endhint %}
