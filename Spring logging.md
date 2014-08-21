## Spring Logging

http://spring.io/blog/2009/12/04/logging-dependencies-in-spring/

Concluzii: 
- spring foloseste commons logging
- daca se doreste log4j se pune commons-logging si log4j
- daca se doreste slf4j se scoate commons-logging si se pune
  - bridge (jcl-over-slf4j)
  - slf4j
  - binding (ex. slf4j-log4j12)
  - implementarea (ex. log4j)

- pe WAS exista deja anumite librarii (commons-logging)
