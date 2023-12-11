> [!NOTE]- query "funkční"
> ```query
> LOAP
> ```

> [!NOTE]+ trika mimo krabici
> 
> ```dataview
> Table krabice as "v krabici"
> From "myDM/Inventář/Skříň/Oblečení/Trika" 
> where !krabice and !used
> ```

> [!NOTE]- trika a kalhoty mimo krabice
> ```dataview
> Table krabice as "v krabici"
> From "myDM/Inventář/Skříň/Oblečení/Trika" or "myDM/Inventář/Skříň/Oblečení/Kalhoty"
> where !krabice
> ```

> [!NOTE]- in krab1
> 
> ```dataview
> list
> from [[krab1]]
> ```




