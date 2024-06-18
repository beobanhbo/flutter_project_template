# Flutter Project Template
This article is intended to introduce Android Studio Code Template and Live code as well as how to use it in real projects. This will increase your working efficiency as well as avoid having to repeat the same action many times - something that should be avoided in programming.

File templates

How to add a new template

Open **Android Studio** and go for **File** → **Settings** → **Editor** → **File and Code Templates**. Or you can search in the Search box to get it directly

By clicking plus in the top right corner, you can add your group of templates or a template to an existing category.


This is a collections flutter file template that used for setup in Android Studio File Template
1. Create file with class name
     ```
       #set( $nameparts = $NAME.split("_"))
       #set( $namepart = '')
       #set( $classname = '')
       #foreach( $namepart in $nameparts )
           #set( $classname = $classname + $namepart.substring(0, 1).toUpperCase() + $namepart.substring(1))
       #end
       
       class ${classname} {}
      ```
      This code will create a file with your input and also generate a class named the same as your file
      Ex: When you create a file named: main_file.dart. The result will be:
      ```
      class MainFile {}
      ```
3. 
1. Cubit template
   1.1 **Cubit**
     ```
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
    ```
     Ex: When you create a file named: demo_cubit.dart. The result will be:
   ```
   class DemoCubit extends Cubit<DemoState>{}
   ```
   1.2 **State**
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
3. # **awdawd**
