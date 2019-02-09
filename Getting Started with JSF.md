# Getting Started with JSF

![Streched](/home/iliass/Pictures/JSF/MVC.png)

## send / receive simple data
**Create the xhtml file**

```xhtml
xmlns:h="http://xmlns.jcp.org/jsf/html"
xmlns:a="http://xmlns.jcp.org/jsf/facelets"
```

**Adding a form**
```
<h:form>
		Name <h:inputText id="name" value="#{theUserName}" 
				a:placeholder="what's your name ?" />
		<br/>
		Age <h:inputText id="age" value="#{theUserAge}" 
				a:placeholder="what's your age ?" />
		
		<h:commandButton value="Submit" action = "myresponse"/>
	</h:form>
```
>submit to *myresponse.xhtml*

**getteing the value in myresponse.xhtml**
```html
        Hello , #{theUserName}
		<br/>
		your age is #{theUserAge}
```

## send / recieve data using beans
1. Create a bean (java class)
> Do not forget 
>* @ManagedBean
>* Default Constructor

2. use the class attribute in xhtml file
> Lower cass the class name



![Streched](/home/iliass/Pictures/JSF/getManagedBean.png)

![Streched](/home/iliass/Pictures/JSF/setManagebean.png)

![Streched](/home/iliass/Pictures/JSF/ALLtogether.png)

