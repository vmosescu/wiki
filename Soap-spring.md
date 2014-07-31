## Soap client cu Spring
### 31.07.204

1. creare model
- din wsdl se scoate schema pt tipurile de date 
(xjc stie doar xsd->java, nu si wsdl->java)
- se ruleaza comanda `xjc -npa -p <package(s)> <schema.xsd>`

2. se face client ws folosind spring-ws
- clientul extinde `org.springframework.ws.client.core.support.WebServiceGatewaySupport`
- se apeleaza metoda `getWebServiceTemplate().marshalSendAndReceive(..)`
- in context se adauga `Jaxb2Marshaller`
