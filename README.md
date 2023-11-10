Juan Sebastian Lozano Siza
### Bloque 1

##### Consultas

1. Listar los nombres de los usuarios

   ```sql
   # Solucion en 'sql'
   SELECT usuario FROM tblUsuarios;
   +---------+
   | usuario |
   +---------+
   | BRE2271 |
   | OSC4677 |
   | JOS7086 |
   | LUI6115 |
   | LUI7072 |
   | DAN2832 |
   | JAQ5351 |
   | ROM6520 |
   | BLA9739 |
   | JES4752 |
   | DIA6570 |
   | RIC8283 |
   | VAL6882 |
   | BRE8106 |
   | LUC4982 |
   | JUA2337 |
   | ELP2984 |
   | JES9640 |
   | LET4015 |
   | LUI1076 |
   | HUG5441 |
   +---------+
   ```

2. Calcular el saldo máximo de los usuarios de sexo “Mujer”

     ```sql
      # Solucion en 'sql'
      SELECT MAX(saldo) AS saldo_maximo_mujeres
      FROM tblUsuarios
      WHERE sexo='M';
      +----------------------+
     | saldo_maximo_mujeres |
     +----------------------+
     |                  500 |
     +----------------------+
     ```

3. Listar nombre y teléfono de los usuarios con teléfono NOKIA, BLACKBERRY o SONY

     ```sql
      # Solucion en 'sql'
      SELECT nombre,telefono
      FROM tblUsuarios
      WHERE marca IN ('NOKIA','BLACKBERRY','SONY');
      +-----------+--------------+
     | nombre    | telefono     |
     +-----------+--------------+
     | JOSE      | 655-143-3922 |
     | LUIS      | 655-100-8260 |
     | DANIEL    | 655-145-2586 |
     | JAQUELINE | 655-330-5514 |
     | DIANA     | 655-143-3952 |
     | VALENTINA | 655-137-4253 |
     | LUCIA     | 655-145-4992 |
     | JESSICA   | 655-330-5143 |
     | LETICIA   | 655-143-4019 |
     | LUIS      | 655-100-5085 |
     +-----------+--------------+
     ```

4. Contar los usuarios sin saldo o inactivos

     ```sql
      # Solucion en 'sql'
      SELECT COUNT(*) AS cantidad_usuarios_sinSaldo_o_Inactivos
      FROM tblUsuarios
      WHERE saldo=0 OR activo=0;
      +----------------------------------------+
     | cantidad_usuarios_sinSaldo_o_Inactivos |
     +----------------------------------------+
     |                                      7 |
     +----------------------------------------+
     ```

5. Listar el login de los usuarios con nivel 1, 2 o 3

     ```sql
      # Solucion en 'sql'
      SELECT usuario
      FROM tblUsuarios
      WHERE nivel IN (1,2,3);
      +---------+
     | usuario |
     +---------+
     | BRE2271 |
     | OSC4677 |
     | JOS7086 |
     | LUI7072 |
     | ROM6520 |
     | JES4752 |
     | DIA6570 |
     | RIC8283 |
     | BRE8106 |
     | LUC4982 |
     | ELP2984 |
     | JES9640 |
     | LET4015 |
     | LUI1076 |
     | HUG5441 |
     +---------+
     ```

6. Listar los números de teléfono con saldo menor o igual a 300

     ```sql
      # Solucion en 'sql'
      SELECT telefono,saldo
      FROM tblUsuarios
      WHERE saldo <= 300;
      +--------------+-------+
     | telefono     | saldo |
     +--------------+-------+
     | 655-330-5736 |   100 |
     | 655-143-4181 |     0 |
     | 655-143-3922 |   150 |
     | 655-137-1279 |    50 |
     | 655-100-8260 |    50 |
     | 655-145-2586 |   100 |
     | 655-330-5514 |     0 |
     | 655-330-3263 |    50 |
     | 655-330-3871 |   100 |
     | 655-143-3952 |   100 |
     | 655-145-6049 |   150 |
     | 655-137-4253 |    50 |
     | 655-100-1351 |   150 |
     | 655-145-4992 |     0 |
     | 655-100-6517 |     0 |
     | 655-330-5143 |   200 |
     | 655-143-4019 |   100 |
     | 655-100-5085 |   150 |
     +--------------+-------+
     ```

7. Calcular la suma de los saldos de los usuarios de la compañia telefónica NEXTEL

     ```sql
      # Solucion en 'sql'
      SELECT SUM(saldo) AS saldos_usuarios_NEXTEL
      FROM tblUsuarios
      WHERE compañia='NEXTEL';
      +------------------------+
     | saldos_usuarios_NEXTEL |
     +------------------------+
     |                    150 |
     +------------------------+
     ```

8. Contar el número de usuarios por compañía telefónica

     ```sql
      # Solucion en 'sql'
      SELECT compañia, COUNT(*) AS numero_usuarios_compañias
      FROM tblUsuarios
      GROUP BY compañia;
      +----------+---------------------------+
     | compañia | numero_usuarios_compañias |
     +----------+---------------------------+
     | IUSACELL |                         6 |
     | TELCEL   |                         3 |
     | MOVISTAR |                         2 |
     | UNEFON   |                         5 |
     | AXEL     |                         2 |
     | AT&T     |                         2 |
     | NEXTEL   |                         1 |
     +----------+---------------------------+
     ```

9. Contar el número de usuarios por nivel

     ```sql
      # Solucion en 'sql'
      SELECT nivel, COUNT(*) AS numero_usuarios_nivel
      FROM tblUsuarios
      GROUP BY nivel;
      +-------+-----------------------+
     | nivel | numero_usuarios_nivel |
     +-------+-----------------------+
     |     2 |                     5 |
     |     3 |                     6 |
     |     0 |                     6 |
     |     1 |                     4 |
     +-------+-----------------------+
     ```

10. Listar el login de los usuarios con nivel 2

       ```sql
        # Solucion en 'sql'
        SELECT usuario AS login
        FROM tblUsuarios
        WHERE nivel = 2;
       +---------+
       | login   |
       +---------+
       | BRE2271 |
       | ROM6520 |
       | RIC8283 |
       | LET4015 |
       | HUG5441 |
       +---------+
       ```

11. Mostrar el email de los usuarios que usan gmail

        ```sql
         # Solucion en 'sql'
         SELECT email
         FROM tblUsuarios
         WHERE email LIKE '%@gmail.com%';
         +---------------------+
        | email               |
        +---------------------+
        | oscar@gmail.com     |
        | francisco@gmail.com |
        | roman@gmail.com     |
        | brenda2@gmail.com   |
        | lucia@gmail.com     |
        +---------------------+
        ```

12. Listar nombre y teléfono de los usuarios con teléfono LG, SAMSUNG o MOTOROLA

      ```sql
       # Solucion en 'sql'
       SELECT nombre,telefono
       FROM tblUsuarios
       WHERE marca IN ('LG','SAMSUNG','MOTOROLA');
       +---------+--------------+
      | nombre  | telefono     |
      +---------+--------------+
      | BRENDA  | 655-330-5736 |
      | OSCAR   | 655-143-4181 |
      | LUIS    | 655-137-1279 |
      | ROMAN   | 655-330-3263 |
      | BLAS    | 655-330-3871 |
      | JESSICA | 655-143-6861 |
      | RICARDO | 655-145-6049 |
      | BRENDA  | 655-100-1351 |
      | JUAN    | 655-100-6517 |
      | ELPIDIO | 655-145-9938 |
      | HUGO    | 655-137-3935 |
      +---------+--------------+
      ```

------

### Bloque 2

##### Consultas

1. Listar nombre y teléfono de los usuarios con teléfono que no sea de la marca LG o SAMSUNG

     ```sql
      # Solucion en 'sql'
      SELECT nombre,telefono
      FROM tblUsuarios
      WHERE marca NOT IN ('LG','SAMSUNG');
      +-----------+--------------+
     | nombre    | telefono     |
     +-----------+--------------+
     | JOSE      | 655-143-3922 |
     | LUIS      | 655-100-8260 |
     | DANIEL    | 655-145-2586 |
     | JAQUELINE | 655-330-5514 |
     | DIANA     | 655-143-3952 |
     | RICARDO   | 655-145-6049 |
     | VALENTINA | 655-137-4253 |
     | BRENDA    | 655-100-1351 |
     | LUCIA     | 655-145-4992 |
     | ELPIDIO   | 655-145-9938 |
     | JESSICA   | 655-330-5143 |
     | LETICIA   | 655-143-4019 |
     | LUIS      | 655-100-5085 |
     | HUGO      | 655-137-3935 |
     +-----------+--------------+
     ```

2. Listar el login y teléfono de los usuarios con compañia telefónica IUSACELL

     ```sql
      # Solucion en 'sql'
      SELECT usuario,telefono
      FROM tblUsuarios
      WHERE compañia='IUSACELL';
      +---------+--------------+
     | usuario | telefono     |
     +---------+--------------+
     | BRE2271 | 655-330-5736 |
     | LUI7072 | 655-100-8260 |
     | ROM6520 | 655-330-3263 |
     | RIC8283 | 655-145-6049 |
     | LUC4982 | 655-145-4992 |
     | JES9640 | 655-330-5143 |
     +---------+--------------+
     ```

3. Listar el login y teléfono de los usuarios con compañia telefónica que no sea TELCEL

     ```sql
      # Solucion en 'sql'
      SELECT usuario,telefono
      FROM tblUsuarios
      WHERE compañia NOT IN ('TELCEL');
     +---------+--------------+
     | usuario | telefono     |
     +---------+--------------+
     | BRE2271 | 655-330-5736 |
     | JOS7086 | 655-143-3922 |
     | LUI7072 | 655-100-8260 |
     | DAN2832 | 655-145-2586 |
     | JAQ5351 | 655-330-5514 |
     | ROM6520 | 655-330-3263 |
     | BLA9739 | 655-330-3871 |
     | DIA6570 | 655-143-3952 |
     | RIC8283 | 655-145-6049 |
     | VAL6882 | 655-137-4253 |
     | BRE8106 | 655-100-1351 |
     | LUC4982 | 655-145-4992 |
     | JUA2337 | 655-100-6517 |
     | ELP2984 | 655-145-9938 |
     | JES9640 | 655-330-5143 |
     | LET4015 | 655-143-4019 |
     | LUI1076 | 655-100-5085 |
     | HUG5441 | 655-137-3935 |
     +---------+--------------+
     ```

4. Calcular el saldo promedio de los usuarios que tienen teléfono marca NOKIA

     ```sql
      # Solucion en 'sql'
      SELECT AVG(saldo) AS saldo_promedio
      FROM tblUsuarios
      WHERE marca='NOKIA';
     +----------------+
     | saldo_promedio |
     +----------------+
     |            100 |
     +----------------+
     ```

5. Listar el login y teléfono de los usuarios con compañia telefónica IUSACELL o AXEL

     ```sql
      # Solucion en 'sql'
      SELECT usuario,telefono
      FROM tblUsuarios
      WHERE compañia IN ('IUSACELL', 'AXEL');
     +---------+--------------+
     | usuario | telefono     |
     +---------+--------------+
     | BRE2271 | 655-330-5736 |
     | LUI7072 | 655-100-8260 |
     | JAQ5351 | 655-330-5514 |
     | ROM6520 | 655-330-3263 |
     | RIC8283 | 655-145-6049 |
     | LUC4982 | 655-145-4992 |
     | JUA2337 | 655-100-6517 |
     | JES9640 | 655-330-5143 |
     +---------+--------------+
     ```

6. Mostrar el email de los usuarios que no usan yahoo

     ```sql
      # Solucion en 'sql'
      SELECT email
      FROM tblUsuarios
      WHERE email NOT LIKE '%@yahoo.com%';
     +-----------------------+
     | email                 |
     +-----------------------+
     | brenda@live.com       |
     | oscar@gmail.com       |
     | francisco@gmail.com   |
     | enrique@outlook.com   |
     | luis@hotmail.com      |
     | daniel@outlook.com    |
     | jaqueline@outlook.com |
     | roman@gmail.com       |
     | blas@hotmail.com      |
     | jessica@hotmail.com   |
     | diana@live.com        |
     | ricardo@hotmail.com   |
     | valentina@live.com    |
     | brenda2@gmail.com     |
     | lucia@gmail.com       |
     | juan@outlook.com      |
     | elpidio@outlook.com   |
     | jessica2@live.com     |
     | luis2@live.com        |
     | hugo@live.com         |
     +-----------------------+
     ```

7. Listar el login y teléfono de los usuarios con compañia telefónica que no sea TELCEL o IUSACELL

     ```sql
      # Solucion en 'sql'
      SELECT usuario,telefono
      FROM tblUsuarios
      WHERE compañia NOT IN ('TELCEL','IUSACELL');
     +---------+--------------+
     | usuario | telefono     |
     +---------+--------------+
     | JOS7086 | 655-143-3922 |
     | DAN2832 | 655-145-2586 |
     | JAQ5351 | 655-330-5514 |
     | BLA9739 | 655-330-3871 |
     | DIA6570 | 655-143-3952 |
     | VAL6882 | 655-137-4253 |
     | BRE8106 | 655-100-1351 |
     | JUA2337 | 655-100-6517 |
     | ELP2984 | 655-145-9938 |
     | LET4015 | 655-143-4019 |
     | LUI1076 | 655-100-5085 |
     | HUG5441 | 655-137-3935 |
     +---------+--------------+
     ```

8. Listar el login y teléfono de los usuarios con compañia telefónica UNEFON

     ```sql
      # Solucion en 'sql'
      SELECT usuario,telefono
      FROM tblUsuarios
      WHERE compañia='UNEFON';
+---------+--------------+
| usuario | telefono     |
+---------+--------------+
| DAN2832 | 655-145-2586 |
| BLA9739 | 655-330-3871 |
| DIA6570 | 655-143-3952 |
| LET4015 | 655-143-4019 |
| LUI1076 | 655-100-5085 |
+---------+--------------+
     ```

9. Listar las diferentes marcas de celular en orden alfabético descendentemente

     ```sql
      # Solucion en 'sql'
       SELECT DISTINCT marca
       FROM tblUsuarios
       ORDER BY marca DESC;
     +------------+
     | marca      |
     +------------+
     | SONY       |
     | SAMSUNG    |
     | NOKIA      |
     | MOTOROLA   |
     | LG         |
     | BLACKBERRY |
     +------------+
     ```

10. Listar las diferentes compañias en orden alfabético aleatorio

       ```sql
        # Solucion en 'sql'
        SELECT DISTINCT compañia
        FROM tblUsuarios
        ORDER BY RAND();
       +----------+
       | compañia |
       +----------+
       | AXEL     |
       | IUSACELL |
       | TELCEL   |
       | NEXTEL   |
       | MOVISTAR |
       | AT&T     |
       | UNEFON   |
       +----------+
       ```

11. Listar el login de los usuarios con nivel 0 o 2

        ```sql
         # Solucion en 'sql'
         SELECT usuario
         FROM tblUsuarios
         WHERE nivel IN (0,2);
        +---------+
        | usuario |
        +---------+
        | BRE2271 |
        | LUI6115 |
        | DAN2832 |
        | JAQ5351 |
        | ROM6520 |
        | BLA9739 |
        | RIC8283 |
        | VAL6882 |
        | JUA2337 |
        | LET4015 |
        | HUG5441 |
        +---------+
        ```

12. Calcular el saldo promedio de los usuarios que tienen teléfono marca LG

      ```sql
       # Solucion en 'sql'
        SELECT AVG(saldo) as saldo_promedio
        FROM tblUsuarios
        WHERE marca='LG';
      +----------------+
      | saldo_promedio |
      +----------------+
      |             50 |
      +----------------+
      ```

------

### Bloque 3

##### Consultas

1. Listar el login de los usuarios con nivel 1 o 3

     ```sql
      # Solucion en 'sql'
       SELECT usuario
       FROM tblUsuarios
       WHERE nivel IN (1,3);
     +---------+
     | usuario |
     +---------+
     | OSC4677 |
     | JOS7086 |
     | LUI7072 |
     | JES4752 |
     | DIA6570 |
     | BRE8106 |
     | LUC4982 |
     | ELP2984 |
     | JES9640 |
     | LUI1076 |
     +---------+
     ```

2. Listar nombre y teléfono de los usuarios con teléfono que no sea de la marca BLACKBERRY

     ```sql
      # Solucion en 'sql'
       SELECT nombre,telefono
       FROM tblUsuarios
       WHERE marca NOT IN ('BLACKBERRY');
     +---------+--------------+
     | nombre  | telefono     |
     +---------+--------------+
     | BRENDA  | 655-330-5736 |
     | OSCAR   | 655-143-4181 |
     | JOSE    | 655-143-3922 |
     | LUIS    | 655-137-1279 |
     | LUIS    | 655-100-8260 |
     | DANIEL  | 655-145-2586 |
     | ROMAN   | 655-330-3263 |
     | BLAS    | 655-330-3871 |
     | JESSICA | 655-143-6861 |
     | DIANA   | 655-143-3952 |
     | RICARDO | 655-145-6049 |
     | BRENDA  | 655-100-1351 |
     | JUAN    | 655-100-6517 |
     | ELPIDIO | 655-145-9938 |
     | JESSICA | 655-330-5143 |
     | LUIS    | 655-100-5085 |
     | HUGO    | 655-137-3935 |
     +---------+--------------+
     ```

3. Listar el login de los usuarios con nivel 3

     ```sql
      # Solucion en 'sql'
      SELECT usuario
      FROM tblUsuarios
      WHERE nivel=3;
     +---------+
     | usuario |
     +---------+
     | OSC4677 |
     | JOS7086 |
     | BRE8106 |
     | LUC4982 |
     | JES9640 |
     | LUI1076 |
     +---------+
     ```

4. Listar el login de los usuarios con nivel 0

     ```sql
      # Solucion en 'sql'
       SELECT usuario
       FROM tblUsuarios
       WHERE nivel=0;
     +---------+
     | usuario |
     +---------+
     | LUI6115 |
     | DAN2832 |
     | JAQ5351 |
     | BLA9739 |
     | VAL6882 |
     | JUA2337 |
     +---------+
     ```

5. Listar el login de los usuarios con nivel 1

     ```sql
      # Solucion en 'sql'
       SELECT usuario
       FROM tblUsuarios
       WHERE nivel=1;
     +---------+
     | usuario |
     +---------+
     | LUI7072 |
     | JES4752 |
     | DIA6570 |
     | ELP2984 |
     +---------+
     ```

6. Contar el número de usuarios por sexo

     ```sql
      # Solucion en 'sql'
       SELECT sexo, COUNT(*) AS numero_usuarios
       FROM tblUsuarios
       GROUP BY sexo;
     +------+-----------------+
     | sexo | numero_usuarios |
     +------+-----------------+
     | M    |               9 |
     | H    |              12 |
     +------+-----------------+
     ```

7. Listar el login y teléfono de los usuarios con compañia telefónica AT&T

     ```sql
      # Solucion en 'sql'
      SELECT usuario, telefono
      FROM tblUsuarios
      WHERE compañia = 'AT&T';
     +---------+--------------+
     | usuario | telefono     |
     +---------+--------------+
     | VAL6882 | 655-137-4253 |
     | HUG5441 | 655-137-3935 |
     +---------+--------------+
     ```

8. Listar las diferentes compañias en orden alfabético descendentemente

     ```sql
      # Solucion en 'sql'
       SELECT DISTINCT compañia
       FROM tblUsuarios
       ORDER BY compañia DESC;
     +----------+
     | compañia |
     +----------+
     | UNEFON   |
     | TELCEL   |
     | NEXTEL   |
     | MOVISTAR |
     | IUSACELL |
     | AXEL     |
     | AT&T     |
     +----------+
     ```

9. Listar el login de los usuarios inactivos

     ```sql
      # Solucion en 'sql'
      SELECT usuario
      FROM tblUsuarios
      WHERE activo=0;
     +---------+
     | usuario |
     +---------+
     | LUI7072 |
     | DIA6570 |
     | VAL6882 |
     | JUA2337 |
     +---------+
     ```

10. Listar los números de teléfono sin saldo

       ```sql
        # Solucion en 'sql' 
        SELECT telefono AS numeros_sin_saldo
        FROM tblUsuarios
        WHERE saldo=0;
       +-------------------+
       | numeros_sin_saldo |
       +-------------------+
       | 655-143-4181      |
       | 655-330-5514      |
       | 655-145-4992      |
       | 655-100-6517      |
       +-------------------+
       ```

11. Calcular el saldo mínimo de los usuarios de sexo “Hombre”

        ```sql
         # Solucion en 'sql'
          SELECT MIN(saldo) AS saldo_minimo_hombres
          FROM tblUsuarios
          WHERE sexo='M';
        +----------------------+
        | saldo_minimo_hombres |
        +----------------------+
        |                    0 |
        +----------------------+
        ```

12. Listar los números de teléfono con saldo mayor a 300

      ```sql
       # Solucion en 'sql'
       SELECT telefono AS numeros_con_saldo_mayor_a_300
       FROM tblUsuarios
       WHERE saldo>300;
      +-------------------------------+
      | numeros_con_saldo_mayor_a_300 |
      +-------------------------------+
      | 655-143-6861                  |
      | 655-145-9938                  |
      | 655-137-3935                  |
      +-------------------------------+
      ```

------

### Bloque 4

##### Consultas

1. Contar el número de usuarios por marca de teléfono

     ```sql
      # Solucion en 'sql'
       SELECT marca, COUNT(*) AS cantidad_de_usuarios
       FROM tblUsuarios
       GROUP BY marca;
     +------------+----------------------+
     | marca      | cantidad_de_usuarios |
     +------------+----------------------+
     | SAMSUNG    |                    4 |
     | LG         |                    3 |
     | NOKIA      |                    2 |
     | SONY       |                    4 |
     | BLACKBERRY |                    4 |
     | MOTOROLA   |                    4 |
     +------------+----------------------+
     ```

2. Listar nombre y teléfono de los usuarios con teléfono que no sea de la marca LG

     ```sql
      # Solucion en 'sql'
       SELECT nombre,telefono
       FROM tblUsuarios
       WHERE marca NOT IN ('LG');
     +-----------+--------------+
     | nombre    | telefono     |
     +-----------+--------------+
     | BRENDA    | 655-330-5736 |
     | JOSE      | 655-143-3922 |
     | LUIS      | 655-137-1279 |
     | LUIS      | 655-100-8260 |
     | DANIEL    | 655-145-2586 |
     | JAQUELINE | 655-330-5514 |
     | JESSICA   | 655-143-6861 |
     | DIANA     | 655-143-3952 |
     | RICARDO   | 655-145-6049 |
     | VALENTINA | 655-137-4253 |
     | BRENDA    | 655-100-1351 |
     | LUCIA     | 655-145-4992 |
     | JUAN      | 655-100-6517 |
     | ELPIDIO   | 655-145-9938 |
     | JESSICA   | 655-330-5143 |
     | LETICIA   | 655-143-4019 |
     | LUIS      | 655-100-5085 |
     | HUGO      | 655-137-3935 |
     +-----------+--------------+
     ```

3. Listar las diferentes compañias en orden alfabético ascendentemente

     ```sql
      # Solucion en 'sql'
      SELECT DISTINCT compañia
      FROM tblUsuarios
      ORDER BY compañia ASC;
     +----------+
     | compañia |
     +----------+
     | AT&T     |
     | AXEL     |
     | IUSACELL |
     | MOVISTAR |
     | NEXTEL   |
     | TELCEL   |
     | UNEFON   |
     +----------+
     ```

4. Calcular la suma de los saldos de los usuarios de la compañia telefónica UNEFON

     ```sql
      # Solucion en 'sql'
      SELECT SUM(saldo) AS saldos_unefon
      FROM tblUsuarios
      WHERE compañia = 'UNEFON';
     +--------------------+
     | saldos_unefon      |
     +--------------------+
     |                550 |
     +--------------------+
     ```

5. Mostrar el email de los usuarios que usan hotmail

     ```sql
      # Solucion en 'sql'
       SELECT email
       FROM tblUsuarios
       WHERE email LIKE '%@hotmail.com%';
     +---------------------+
     | email               |
     +---------------------+
     | luis@hotmail.com    |
     | blas@hotmail.com    |
     | jessica@hotmail.com |
     | ricardo@hotmail.com |
     +---------------------+
     ```

6. Listar los nombres de los usuarios sin saldo o inactivos

     ```sql
      # Solucion en 'sql'
      SELECT nombre
      FROM tblUsuarios
      WHERE saldo=0 OR activo=0;
     +-----------+
     | nombre    |
     +-----------+
     | OSCAR     |
     | LUIS      |
     | JAQUELINE |
     | DIANA     |
     | VALENTINA |
     | LUCIA     |
     | JUAN      |
     +-----------+
     ```

7. Listar el login y teléfono de los usuarios con compañia telefónicaIUSACELL o TELCEL

     ```sql
      # Solucion en 'sql'
       SELECT usuario AS login,telefono
       FROM tblUsuarios
       WHERE compañia IN ('USACELL','TELCEL');
     +---------+--------------+
     | login   | telefono     |
     +---------+--------------+
     | OSC4677 | 655-143-4181 |
     | LUI6115 | 655-137-1279 |
     | JES4752 | 655-143-6861 |
     +---------+--------------+
     ```

8. Listar las diferentes marcas de celular en orden alfabético ascendentemente

     ```sql
      # Solucion en 'sql'
      SELECT DISTINCT marca
      FROM tblUsuarios
      ORDER BY marca ASC;
     +------------+
     | marca      |
     +------------+
     | BLACKBERRY |
     | LG         |
     | MOTOROLA   |
     | NOKIA      |
     | SAMSUNG    |
     | SONY       |
     +------------+
     ```

9. Listar las diferentes marcas de celular en orden alfabético aleatorio

     ```sql
      # Solucion en 'sql'
      SELECT DISTINCT marca
      FROM tblUsuarios
      ORDER BY RAND();
     +------------+
     | marca      |
     +------------+
     | BLACKBERRY |
     | SONY       |
     | MOTOROLA   |
     | NOKIA      |
     | LG         |
     | SAMSUNG    |
     +------------+
     ```

10. Listar el login y teléfono de los usuarios con compañia telefónica IUSACELL o UNEFON

       ```sql
        # Solucion en 'sql'
        SELECT usuario AS login,telefono
        FROM tblUsuarios
        WHERE compañia IN ('IUSACELL','UNEFON');
       +---------+--------------+
       | login   | telefono     |
       +---------+--------------+
       | BRE2271 | 655-330-5736 |
       | LUI7072 | 655-100-8260 |
       | DAN2832 | 655-145-2586 |
       | ROM6520 | 655-330-3263 |
       | BLA9739 | 655-330-3871 |
       | DIA6570 | 655-143-3952 |
       | RIC8283 | 655-145-6049 |
       | LUC4982 | 655-145-4992 |
       | JES9640 | 655-330-5143 |
       | LET4015 | 655-143-4019 |
       | LUI1076 | 655-100-5085 |
       +---------+--------------+
       ```

11. Listar nombre y teléfono de los usuarios con teléfono que no sea de la marca MOTOROLA o NOKIA

        ```sql
         # Solucion en 'sql'
          SELECT nombre,telefono
          FROM tblUsuarios
          WHERE marca NOT IN ('MOTOROLA','NOKIA');
        +-----------+--------------+
        | nombre    | telefono     |
        +-----------+--------------+
        | BRENDA    | 655-330-5736 |
        | OSCAR     | 655-143-4181 |
        | LUIS      | 655-137-1279 |
        | DANIEL    | 655-145-2586 |
        | JAQUELINE | 655-330-5514 |
        | ROMAN     | 655-330-3263 |
        | BLAS      | 655-330-3871 |
        | JESSICA   | 655-143-6861 |
        | DIANA     | 655-143-3952 |
        | VALENTINA | 655-137-4253 |
        | LUCIA     | 655-145-4992 |
        | JUAN      | 655-100-6517 |
        | JESSICA   | 655-330-5143 |
        | LETICIA   | 655-143-4019 |
        | LUIS      | 655-100-5085 |
        +-----------+--------------+
        ```

12. Calcular la suma de los saldos de los usuarios de la compañia telefónica TELCEL

      ```sql
       # Solucion en 'sql'
       SELECT SUM(saldo) as saldo_usuarios_TELCEL
       FROM tblUsuarios
       WHERE compañia='TELCEL';
      +-----------------------+
      | saldo_usuarios_TELCEL |
      +-----------------------+
      |                   550 |
      +-----------------------+
      ```
