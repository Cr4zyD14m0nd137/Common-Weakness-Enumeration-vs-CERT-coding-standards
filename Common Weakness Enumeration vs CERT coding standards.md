# Common Weakness Enumeration vs CERT coding standards

## Similitudes

### CWE
El CWE es un diccionario de tipos de debilidades de seguridad comunes en el software y las mejores prácticas asociadas para evitar esas debilidades. Proporciona un orden de debilidades de seguridad que ayuda a los desarrolladores y profesionales de seguridad a comprender y abordar problemas de seguridad en el software.

### CERT Secure Coding Standards
Los CERT Secure Coding Standards son un conjunto de reglas para escribir código seguro en varios lenguajes de programación. Estos estándares son mantenidos por el CERT Coordination Center y se centran en la prevención de debilidades de seguridad comunes.

### Debilidad CWE-79 (Improper Neutralization of Input During Web Page Generation 'Cross-site Scripting' - XSS):
Falta de neutralización de entrada en aplicaciones web, lo que puede llevar a ataques de XSS. El estándar del CERT que se relaciona con esto podría ser:

Estándar CERT C++ Coding Standard, SEI CERT C Coding Standard, o similar, que incluye pautas para la manipulación segura de datos de entrada en aplicaciones web.
Ejemplo de código vulnerable (en C++):

`std::string user_input = GetInputFromUser();`

**`std::cout << "Hello, " << user_input << "!";`**

El script malicioso se encuentra en el user_input, se ejecutará sin ninguna neutralización de entrada.

En este caso, si el usuario ingresa un script malicioso en user_input, se ejecutará sin ninguna neutralización de entrada.

### Debilidad CWE-134 (Use of Externally-Controlled Format String):
Esta debilidad implica el uso de cadenas de formato controladas externamente, que pueden llevar a vulnerabilidades de formato de cadena. El estándar del CERT relacionado podría ser:

Estándar CERT C Coding Standard, que incluye pautas sobre el uso seguro de cadenas de formato.
Ejemplo de código vulnerable (en C):

`char user_input[100];`

`scanf(user_input);`

**`printf(user_input);  // Vulnerable a ataques de formato de cadena`**

En este caso, si un atacante proporciona un valor malicioso como entrada, puede explotar la vulnerabilidad de formato de cadena.

### En este caso, si un atacante proporciona un valor malicioso como entrada, puede explotar la vulnerabilidad de formato de cadena:
Esta debilidad involucra la manipulación insegura de consultas SQL. El estándar del CERT relacionado podría ser:

Estándar CERT Oracle Secure Coding Standard, que incluye pautas específicas para evitar la inyección de SQL en aplicaciones que utilizan bases de datos Oracle.
Ejemplo de código vulnerable (en Java):

`String userInput = request.getParameter("username");`

**`String sqlQuery = "SELECT * FROM users WHERE username = '" + userInput + "'";`**

En este caso, si el valor de userInput contiene una consulta SQL maliciosa, se producirá una inyección de SQL.