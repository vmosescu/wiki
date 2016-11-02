#JMS

Citirea mesajelor de pe coada se poate face:
- sincron: se apeleaza metoda **receive** (ramane blocata pana cand vone un mesaj, deci e bine sa fie apelata cu *timeout*)
- asincron: se inregistreaza un **message listener** la consumator. MDB este un asemenea *message listener* in containerul EJB

Spring foloseste citirea sincrona, dar o face intr-o bucla. 
Dpdv al programatorului este tot o citire asincrona, el inregistrand un listener: [DefaultMessageListenerContainer](http://docs.spring.io/spring/docs/current/javadoc-api/org/springframework/jms/listener/DefaultMessageListenerContainer.html)
