# Flutter Project Template
This article is intended to introduce Android Studio Code Template and Live code as well as how to use it in real projects. This will increase your working efficiency as well as avoid having to repeat the same action many times - something that should be avoided in programming.

**I. File templates**

**How to add a new template**

Open **Android Studio** and go for **File** → **Settings** → **Editor** → **File and Code Templates**. Or you can search in the **Search box** to get it directly.


![alt text](https://github.com/beobanhbo/flutter_project_template/blob/main/Screenshot%202024-06-18%20at%2023.13.39.png)

By clicking plus in the top left corner, you can create your templates. Input the name of it and the file extension that it will be created. In this case we are creating a **Dart file**, so the **Extension field** will be _**dart**_.

![alt text](https://github.com/beobanhbo/flutter_project_template/blob/main/Screenshot%202024-06-18%20at%2023.17.34.png)

For example, i want to create a template like this:

![alt text](https://github.com/beobanhbo/flutter_project_template/blob/main/Screenshot%202024-06-18%20at%2023.25.08.png)

I named **"_Example to create Dart template file_"**, with extension is **_dart_**. Then input the content you want to generate in the box right below. I will set it "// Hello". Don't forget to save it.

When it done, go to a folder/ directory you want to create that file. **Right click** → **New**, you will see the _**Example to create Dart template file**_ option. Select it, set a name and click **OK** to create it.

![alt text](https://github.com/beobanhbo/flutter_project_template/blob/main/Screenshot%202024-06-18%20at%2023.30.02.png)

As you can see, a file will be created:

![alt text](https://github.com/beobanhbo/flutter_project_template/blob/main/Screenshot%202024-06-18%20at%2023.36.34.png)

**Create content for template**

In file templates, you can use text, code, comments, and predefined variables. A list of predefined variables is available below. When you use these variables in templates, they expand into corresponding values later in the editor.  It is also possible to specify custom variables. Custom variables use the following format: **${VARIABLE_NAME}**, where **VARIABLE_NAME** is a name for your variable (for example, **${MY_CUSTOM_FUNCTION_NAME}**). Before the IDE creates a new file with custom variables, you see a dialog where you can define values for custom variables in the template.

This is a list of predefined variables that Android Studio created.

| Predefined variable |Explain  |
|--|--|
| ${DAY} |Current day of the month  |
| ${DAY_NAME_SHORT} |First three letters of the current day name (Mon, Tue, and so on)|
| ${DAY_NAME_FULL} |Full name of the current day (Monday, Tuesday, and so on)|
| ${DIR_PATH} |Path to the directory of the new file (relative to the project root)|
| ${FILE_NAME} |Name of the new file|
| ${HOUR} |Current hour|
| ${MINUTE} |Current minute|
| ${SECOND} |Current second|
| ${NAME} |Name of the new entity (file, type, interface, and so on)|


I will create a template to create a class. Check this code below:

![alt text](https://github.com/beobanhbo/flutter_project_template/blob/main/Screenshot%202024-06-18%20at%2023.56.18.png)

After choose the template, set the name and see the result.

![alt text](https://github.com/beobanhbo/flutter_project_template/blob/main/Screenshot%202024-06-18%20at%2023.59.09.png)

The file name will be set as class name:

![alt text](https://github.com/beobanhbo/flutter_project_template/blob/main/Screenshot%202024-06-19%20at%2000.01.51.png)

But, the is one thing seems not good. Exactly, the class name is not in right format, it should be **"DemoCreateClassFile"**. So, lets update our template with this code below:

```
#set( $nameparts = $NAME.split("_"))
#set( $namepart = '')
#set( $classname = '')
#foreach( $namepart in $nameparts )
    #set( $classname = $classname + $namepart.substring(0, 1).toUpperCase() + $namepart.substring(1))
#end

class ${classname} {}
```

 And tada!!!, everything looks good now.
 
![alt text]( https://github.com/beobanhbo/flutter_project_template/blob/main/Screenshot%202024-06-19%20at%2000.06.33.png)


This is a collections flutter file template that used for setup in Android Studio File Template

**1. Create file with class name**

       #set( $nameparts = $NAME.split("_"))
       #set( $namepart = '')
       #set( $classname = '')
       #foreach( $namepart in $nameparts )
           #set( $classname = $classname + $namepart.substring(0, 1).toUpperCase() + $namepart.substring(1))
       #end
       
       class ${classname} {}
    
      
  This code will create a file with your input and also generate a class named the same as your file
  Ex: When you create a file named: main_file.dart. The result will be:
  

      class MainFile {}
**2. Create file with abstract class name**

       #set( $nameparts = $NAME.split("_"))
       #set( $namepart = '')
       #set( $classname = '')
       #foreach( $namepart in $nameparts )
           #set( $classname = $classname + $namepart.substring(0, 1).toUpperCase() + $namepart.substring(1))
       #end
       
      abstract class ${classname} {}
      
**3. Create enum file**

       #set( $nameparts = $NAME.split("_"))
       #set( $namepart = '')
       #set( $classname = '')
       #foreach( $namepart in $nameparts )
           #set( $classname = $classname + $namepart.substring(0, 1).toUpperCase() + $namepart.substring(1))
       #end
       
      enum ${classname} {}     
**4. Create mixin file**

       #set( $nameparts = $NAME.split("_"))
       #set( $namepart = '')
       #set( $classname = '')
       #foreach( $namepart in $nameparts )
           #set( $classname = $classname + $namepart.substring(0, 1).toUpperCase() + $namepart.substring(1))
       #end
       
      mixin ${classname} {}  

**5. Create extension file**

    #set( $nameparts = $NAME.split("_"))
    #set( $namepart = '')
    #set( $classname = '')
    #foreach( $namepart in $nameparts )
        #set( $classname = $classname + $namepart.substring(0, 1).toUpperCase() + $namepart.substring(1))
    #end
    #set( $datatype = $DATA_TYPE)
    extension ${classname} on ${datatype}{}

**6. Cubit template**

   **6.1 Cubit**

          #set( $nameparts = $NAME.split("_"))
          #set( $namepart = '')
          #set( $classname = '')
          #set( $stateclassname = '')
          #foreach( $namepart in $nameparts )
              #if($namepart.toLowerCase()!='cubit')
                  #set( $stateclassname = $stateclassname + $namepart.substring(0, 1).toUpperCase() + $namepart.substring(1))
              #end
               #set( $classname = $classname + $namepart.substring(0, 1).toUpperCase() + $namepart.substring(1))
          #end
          
          import 'package:flutter_bloc/flutter_bloc.dart';
          class ${classname} extends Cubit<${stateclassname}State>{
          
          }
   
 
 Ex: When you create a file named: demo_cubit.dart. The result will be:
   ```
   class DemoCubit extends Cubit<DemoState>{}
   ```
**6.2 State**

   I created a basic state in Cubit. That included **Init**, **Loading** and **Error** state 
   
   ```
   #set( $nameparts = $NAME.split("_"))
   #set( $namepart = '')
   #set( $classname = '')
   #foreach( $namepart in $nameparts )
       #set( $classname = $classname + $namepart.substring(0, 1).toUpperCase() + $namepart.substring(1))
   #end
   
   abstract class ${classname} {}
   class Init${classname} extends ${classname}{}
   class Loading${classname} extends ${classname}{}
   class Error${classname} extends ${classname}{}
   ```
# **II. Live template**

 Using Live templates to insert common constructs into your code, such as loops, conditions, declarations, or print statements.
 
To expand a code snippet, type the corresponding template abbreviation and press **Tab**. Keep pressing **Tab** to jump from one variable in the template to the next one. Press 
**LShift** and **Tab** to move to the previous variable.

**Types of live templates**

- **Simple templates**: contain only fixed plain text. When you expand a simple template, the text is automatically inserted into your source code, replacing the abbreviation. Ex: Type **sout** then press **Tab**, IDE will add the code like this **print();** then you can insert the text in the brace

- **Parameterized templates**: contain variables that enable user input. When you expand a parameterized template, variables are either replaced by input fields for the user to specify manually, or calculated by IntelliJ IDEA automatically. Ex: Type **fori** then press **Tab**, IDE will add the code like this :

    ```
    for (int i = 0; i < ; i++) {
    
    }
    ```

**Configure live templates**

Open **Android Studio** and go for **File** → **Settings** → **Editor** → **Live Templates**. Or you can search in the **Search box** to get it directly.

![alt text](https://github.com/beobanhbo/flutter_project_template/blob/main/Screenshot%202024-06-23%20at%2022.39.25.png)


**Create live templates**
- Select the template group where you want to create a new live template
- Click the Add button and select Live Template
![alt text](https://github.com/beobanhbo/flutter_project_template/blob/main/Screenshot%202024-06-23%20at%2022.43.02.png)
- Specify the context in which the template will be available. By default, no context is specified and IntelliJ IDEA displays a message at the bottom of the dialog:

- Click Define below the message and select the checkboxes next to applicable contexts

![alt text](https://github.com/beobanhbo/flutter_project_template/blob/main/Screenshot%202024-06-23%20at%2022.43.02.png)

- In the Abbreviation field, specify the characters that will be used to expand the template. For example: todo.
- In the Template text field, specify the body of the template with variables.
- Apply all your changes.

This is a collections flutter file template that used for setup in Android Studio File Template

**1. Create a Try- Catch**
```
try{

}
catch(e,s){

}

```

**2. Create SizedBox with Height**

```
const SizedBox(height: $VAR$),
```

**3. Create SizedBox with Width**

```
const SizedBox(width: $VAR$),
```

**4. Create BLoc Consumer**

```
BlocConsumer(
bloc: $var$,
listener: (context, state) {
    
    },
    builder:   (context, state) {
        $END$
    },

),
```

**5. Create Gesture Detector with onTap**

```
  GestureDetector(
              onTap: () {
                $function$();
              },
            ),
```
**6. Create void function with async**

```
void $var$()async{
}
```

**7. Create ValueListenableBuilder**

```
 ValueListenableBuilder(
              valueListenable: $value$,
              builder: (BuildContext context, value, Widget? child) {
                return $END$
              },
            ),

```

**8. Create StreamBuilder**

```
 StreamBuilder(
              stream: $var$,
              builder:
                  (BuildContext context, AsyncSnapshot<dynamic> snapshot) {
                if (!snapshot.hasData) return const SizedBox();
                return $END$
              },
            ),

```


