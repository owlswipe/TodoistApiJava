# TodoistApiJava
This is simple and lightweight unofficial library by Gittoks

Todoist web site - https://todoist.com

[Download release JAR library](https://github.com/Gittoks/TodoistApiJava/releases)
This TodoistApiJava library user simple-json 1.1

## How to use

***Todoist Reader***: read projects
```java

String token = "Your todoist token here";

TodoistReader tr = new TodoistReader(token);

try {
    ArrayList<TodoistProject> projects = tr.readProjects();
    for (TodoistProject project :
            projects) {
        System.out.println(project.getName() + " : " + project.getId() + " : " + project.getIndent());
    }
} catch (ParseException e) {
    System.err.println("Erorr");
}
```

**OUTPUT**
```
Inbox : 125065255 : 1
Project 1 : 125065256 : 1
Project 2 : 125065257 : 1
Project 3 : 125065258 : 2
.....
```
<hr>

***Todoist Writter***: write item
```java
String token = "Your todoist token here";
long project_id = 12312; // "Your project id (get it from TodoistReader)"

TodoistWriter wr = new TodoistWriter(token);

wr.writeItem("New item from Gittoks API", project_id);
```
<hr>

***TodoistReader***: read all items (or all items in project)
```java
try {
    ArrayList<TodoistItem> items = tr.readItems();
    for (TodoistItem item :
            items) {
        System.out.println(item.getContent());
    }
} catch (ParseException e) {
    System.err.println("Error");
}
```
<hr>

#### Fork and use my library)
