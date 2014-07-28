Spring DataBinder
20 iunie 2013

- In DataBinder se pot inregistra PropertyEditors. (in spring 3 se pot folosi si Converter)
Ei se inregistreaza de obicei pe metoda initBinder. Acestia se creaza in acel moment, nu se inregistreaza in containerul spring. Asta pt ca ei trebuie nu trebuie sa fie singleton: nu sunt thread safety (ex. SimpleDateFormat).

- Mai mult: daca se inregistreaza un PropertyEditor pt un tip de clasa si avem in obiect mai multe proprietati de acest tip de clasa, atunci acesta este folosit pt toate proprietatile. Este ok cand se face transformarea din String in obiectul respectiv (se apeleaza metoda setAsText). Problema este ca acest Property Editor are setata ca valoare ultima proprietate pe care a setat-o, astfel ca daca se apeleaza metoda propertyEditor.getAsText, ea va returna mereu ultima valoare. 

- TO DO: cum se foloseste DataBinder in aplicatii web pt intoarcerea in formular in cazul unor erori de validare?
Ex. Avem un formular cu 2 campuri de data. Formularul are 2 proprietati de tip Date. In validari vedem ca nu e corect ce a introdus utilizatorul (o data prea mare) si trebuie sa ne intoarcem in formular cu un mesaj de eroare, dar sa precompletam data respectiva cu ce a introdus utilizatorul anterior (adica sa convertim acum proprietatea de tip Date in String)
