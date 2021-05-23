# REDIS_BASIC_list
Basic commands on REDIS using Docker-Compose

- Create the key "views:ultimo_usuario" with values (Carlos, Joao, Ana, Carol)
As we want to work with List, we should use the ```PUSH``` command to add the key and values, as shown in image below:

![1-Inserindo_chave_valor](https://user-images.githubusercontent.com/62483710/119210081-c47c6900-ba80-11eb-89a0-5a0cde7b5219.PNG)


 - Here, we want to it to show the whole list named ```views:ultimo_usuario``` , so we do it using the command ```lrange views:ultimo_usuário 0 -1```. The numbers 0 and -1 means the index of the range of position we want to show. 
 - Then we use the command ```lrange views:ultimo_usuario 0 -2``` to show the whole list but the last.
 - Next we use the command ```llen views:ultimo_usuario``` to show the lengh of the list
 - After shown the size of the list, we want to redefine the size of the list using the ```ltrim``` command, excluding the first element in the list. the command used is ``` ltrim views:ultimo_usuario 1 -1```
 - Last, we check the whole list using ```lrange views:ultimo_usuario 0 -1```
 - Hte code is shown below:

![2-manipulando_valor](https://user-images.githubusercontent.com/62483710/119270485-3d8bd580-bbd3-11eb-84fb-553c065defe9.PNG)

-Now the goal is to remove the first elmenet is the list and we do it using the ```lpop``` command. Then, to remove the last element we use the ```rpop``` command. Sometimes, when the list is empty, the return is Null, so to avoid this we can set a time, in seconds, before this Null reponse. It's donw by ```brpop``` or ```blpop```, as shown below:

![3-redefinido_lista](https://user-images.githubusercontent.com/62483710/119271281-467ea600-bbd7-11eb-9416-a8769ab29bde.PNG)

