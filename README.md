# Flutter Project Template

This is a collections flutter file template that used for setup in Android Studio File Template

1. Cubit template
   1.1 Cubit
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
   1.2 State
3. # **awdawd**
