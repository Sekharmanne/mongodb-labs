## Create a Person POJO

Open up a new java class called `Person` in your IDE or text editor.  Store this in a new file called `Person.java`

Here is the contents of the file

```java
package com.example.accessingmongodbdatarest;

import org.springframework.data.annotation.Id;

public class Person {

	@Id private String id;

	private String firstName;
	private String lastName;

	public String getFirstName() {
		return firstName;
	}

	public void setFirstName(String firstName) {
		this.firstName = firstName;
	}

	public String getLastName() {
		return lastName;
	}

	public void setLastName(String lastName) {
		this.lastName = lastName;
	}
}
```
