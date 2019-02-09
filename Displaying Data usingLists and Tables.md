# Displaying Data usingLists and Tables

## Displaying Data using lists
![Streched](/home/iliass/Pictures/JSF/S6L34.png)
![Streched](/home/iliass/Pictures/JSF/S6L34-2.png)

> student_list_demo.xhtml
```html
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml"
      xmlns:h="http://java.sun.com/jsf/html"
      xmlns:a="http://xmlns.jcp.org/jsf/facelets"
      xmlns:f="http://java.sun.com/jsf/core"
      xmlns:ui="http://java.sun.com/jsf/facelets">
<h:head>
		<title>Counter One - </title>
	
</h:head>

<h:body>
<h3>Student list Demo</h3>
	<hr/>
	<ul>
		<ui:repeat var="tempstudent" value="#{studentDataUtil.students}">
			<li> #{tempstudent.firstName} #{tempstudent.lastName}  </li>
		
		</ui:repeat>
	</ul>
	
	
</h:body>
</html>

```
> StendentDataUtil.java
```java
package com.iliass.beans;
import java.util.ArrayList;
import java.util.List;

import javax.faces.bean.ManagedBean;
import javax.faces.bean.SessionScoped;

import com.iliass.beans.*;


@ManagedBean
@SessionScoped
public class StudentDataUtil {
	
	private List<Student> students ;
	
	public StudentDataUtil() {
		// TODO Auto-generated constructor stub
		loadSampleData();
	}	
	
	public void loadSampleData() {
		students = new ArrayList<>() ;
		
		students.add(new Student("iliass" , "aek" , "iliassaek@gmail.com") ) ;
		students.add(new Student("anass" , "aek" , "anassaek@gmail.com")) ;
		students.add(new Student("detroit", "Human Robot", "detroit2018@gmail.com") ) ;
		
	}

	public List<Student> getStudents() {
		return students;
	}
	
	

}

```

> Student.java
```java
package com.iliass.beans;

import javax.faces.bean.ManagedBean;

@ManagedBean
public class Student {
	
	
	private String firstName ;
	private String lastName ;
	private String email ;
	
	
	
	
	public Student(String firstName, String lastName, String email) {
		this.firstName = firstName;
		this.lastName = lastName;
		this.email = email;
	}
	public String getFirstName() {
		return firstName;
	}
	public String getEmail() {
		return email;
	}
	public void setEmail(String email) {
		this.email = email;
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
![Streched](/home/iliass/Pictures/JSF/S6L35-1.png)
![Streched](/home/iliass/Pictures/JSF/S6L35-2.png)
![Streched](/home/iliass/Pictures/JSF/S6L35-3.png)
> student_table_demo.xhtml
```html
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml"
      xmlns:h="http://java.sun.com/jsf/html"
      xmlns:a="http://xmlns.jcp.org/jsf/facelets"
      xmlns:f="http://java.sun.com/jsf/core"
      xmlns:ui="http://java.sun.com/jsf/facelets">
<h:head>
		<title>Student Table demo </title>
	
</h:head>

<h:body>
<h3>Student Table Demo</h3>
	<hr/>
	<br/>
	
	<h:dataTable value="#{studentDataUtil.students}" var="tempStudent" border="1">
	
		<h:column>
			<!--  column header  -->
			<f:facet name="header">First Name </f:facet>
			
			<!-- Value of each row -->
			#{tempStudent.firstName}
		</h:column>
		
		<h:column>
			<!--  column header  -->
			<f:facet name="header">Last Name </f:facet>
			
			<!-- Value of each row -->
			#{tempStudent.lastName}
		</h:column>
		
		<h:column>
			<!--  column header  -->
			<f:facet name="header">Email </f:facet>
			
			<!-- Value of each row -->
			#{tempStudent.email}
		</h:column>				
	
	
	</h:dataTable>
	
	
</h:body>
</html>
```

## Applying CSS Styles to Tables
![Streched](/home/iliass/Pictures/JSF/S6L36-1.png)
![Streched](/home/iliass/Pictures/JSF/S6L36-2.png)
![Streched](/home/iliass/Pictures/JSF/S6L36-3.png)
![Streched](/home/iliass/Pictures/JSF/S6L36-4.png)


```html
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml"
      xmlns:h="http://java.sun.com/jsf/html"
      xmlns:a="http://xmlns.jcp.org/jsf/facelets"
      xmlns:f="http://java.sun.com/jsf/core"
      xmlns:ui="http://java.sun.com/jsf/facelets">
<h:head>
		<title>Student Table demo </title>
	<h:outputStylesheet name="student_table_demo.css"></h:outputStylesheet>
</h:head>

<h:body>
<h3>Student Table Demo</h3>
	<hr/>
	<br/>
	
	<h:dataTable value="#{studentDataUtil.students}" var="tempStudent" border="1"
	styleClass="demo-table"
	headerClass="demo-table-header"
	rowClasses="demo-table-odd-row, demo-table-even-row">
	
		<h:column>
			<!--  column header  -->
			<f:facet name="header">First Name </f:facet>
			
			<!-- Value of each row -->
			#{tempStudent.firstName}
		</h:column>
		
		<h:column>
			<!--  column header  -->
			<f:facet name="header">Last Name </f:facet>
			
			<!-- Value of each row -->
			#{tempStudent.lastName}
		</h:column>
		
		<h:column>
			<!--  column header  -->
			<f:facet name="header">Email </f:facet>
			
			<!-- Value of each row -->
			#{tempStudent.email}
		</h:column>				
	
	
	</h:dataTable>
	
	
</h:body>
</html>
```

```css
.demo-table {   
	border-collapse:collapse;
	border-bottom:1px solid gray;
	font-family: Tahoma,Verdana,Segoe,sans-serif;
}
 
.demo-table-header {
	border-bottom:1px solid gray;
	background:none repeat scroll 0 0 #66CCFF;
	padding:10px;
}
 
.demo-table-odd-row {
	border-top:1px solid gray;
	background:none repeat scroll 0 0 #FFFFFFF;
	text-align:center;
}
 
.demo-table-even-row {
	border-top:1px solid gray;
	background:none repeat scroll 0 0 #F9F9F9;
	text-align:center;
}
```