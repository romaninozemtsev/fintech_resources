# fintech_resources
Curated list of Fintech resources

## Basics

### Idempotency

>    A request method is considered "idempotent" if the intended effect on
   the server of multiple identical requests with that method is the
   same as the effect for a single such request.  Of the request methods
   defined by this specification, PUT, DELETE, and safe request methods
   are idempotent. 
(from https://tools.ietf.org/html/rfc7231#section-4.2.2)

Idempotency is one of the most used buzzwords, but Payments is a domain where idempotency is very important, and can't be taken lightly.

* Stripe API reference: https://stripe.com/docs/api/idempotent_requests
* Adyen API: https://docs.adyen.com/development-resources/api-idempotency
* Stripe article about idempotency: https://stripe.com/blog/idempotency

### Accounting

Double entry accounting: 
https://en.wikipedia.org/wiki/Double-entry_bookkeeping_system

1. Martin Fowler old but good articles:
   1. https://martinfowler.com/eaaDev/AccountingNarrative.html
   2. https://martinfowler.com/eaaDev/AccountingTransaction.html
2. foundation of NuBank architecture: https://www.infoq.com/presentations/nubank-financial-systems
3. Square's "Books" approach to dountry entry accounting: https://www.youtube.com/watch?v=I_Pt_i3ntGw

### Domain Driven Design(DDD)

99% of engineers don't need DDD; until you start touching actually complicated business domains like e-commerce or banking.



### Event driven vs worfkflows 

one opinion from workflow product creators:
https://www.infoq.com/presentations/event-flow-distributed-systems


###  Payments glossary

Adyen: https://docs.adyen.com/payments-essentials/payment-glossary


### PCI / Card data handling


1. stripe: https://www.infoq.com/presentations/stripe-api-pci/ (starting from 19th minute)
2. netflix: https://youtu.be/sYFDnGjNVrk?t=120 (from 2 minutes)


## Podcasts

1. Starling developer podcast (https://itunes.apple.com/us/podcast/starling-developer-podcast/id1274198025?mt=2)


### Specific podcast episodes

## By Company

### uber
https://www.youtube.com/watch?v=Dz6dAZs8Scg
https://www.youtube.com/watch?v=XzJDNg_iSaA

### stripe
https://www.infoq.com/presentations/stripe-api-pci

### netflix
https://youtu.be/sYFDnGjNVrk?t=120

### N26
1. video + transcript
https://community.risingstack.com/how-n26-built-a-modern-banking-software-with-javascript-microservices/#q5
2. podcast
https://softwareengineeringdaily.com/2018/07/18/build-a-bank-n26-with-pat-kua/

summary:
(CTO was a consultant for thoughtwofks consulting for Banks)
* cloud
* mostly JVM, before Java, now moving to Kotlin
* one monolith, many microservices. springboot, maven, jenkins;
* infra as code; hashicorp - nomad,saltstack; consul; vault;
* docker as containers; 
* centralized logging through ELK;
* continuous delivery;

### robinhood
https://www.youtube.com/watch?v=RVr3NldzmcY&t=3s

### nubank
https://www.infoq.com/presentations/nubank-financial-systems

summary:
a. kafka as event bus for all async communication
b. datomic as database (append only database like git, ACID)
c. rest for API.
d. microservices.
e. closure (functional JVM language)
f. 90 services. come and go. lots of cross-service dependencies.
g. accounting as a main domain model. kafka as event sourcing for accounting.
model:
core accounting:
- book account (one balance sheet of a customer)
- entry - pair of debit and a credit to two book-accounts
- balance - sum of entries of a book-account

- movement - group of entries (like payment arrived).
- meta-entity - external entity originating movement


principles:
- event driven
- availability
- traceability
resiliency

ideal model:
Kafka -> f(payload) = movement -> TX to DB.

6. Starling Bank
https://www.infoq.com/presentations/cloud-based-bank-java

amazon RDS.

1. vanilla java without any frameworks.
2. services don't have sync communications. only async.
3. only mobile api does scatter across services.
4. asyncronous, idempotentm, retriable steps in the worklows. some custom built engine. no kafka or similar.


starling bank again
https://www.infoq.com/presentations/starling-bank-resilience


### klarna
https://vimeo.com/70854665
https://softwareengineeringdaily.com/2018/08/10/klarna-engineering-with-marcus-granstrom/

use Kafka for all async communications. 





## Blogs
https://robinhood.engineering/


## Articles
https://medium.com/airbnb-engineering/tracking-the-money-scaling-financial-reporting-at-airbnb-6d742b80f040

## shopify
address normalization at shopify
https://engineering.shopify.com/blogs/engineering/handling-addresses-from-all-around-the-world


| company | industry | languages | DB | queue tech | comments |
| --- | --- | --- | --- | --- | --- | 
| starling bank  | bank | java | RDS  | workflow engine | ....  |
| nubank | bank | closure | datomic | kafka | ... |
| N26 | bank | ... | ... | ... | ... |
| simple | bank | ... | ... | ... | ... |
| monzo | bank | ... | ... | ... | ... |
| n26 | bank | java/kotlin | mysql | ... | ... |
| tandem | bank | ... | ... | ... | ... |
| varo money | bank | ... | ... | ... | ... |
| netflix | payments | ... | ... | ... | ... |
| stripe | payments | ... | ... | ... | ... |
| uber | payments | java | dynamo | kafka | ... |
| airbnb | payments | ... | ... | ... | ... |
| facebook | payments | ... | ... | ... | ... |
| transferwise | remittances | ... | ... | ... | ... |
| klarna  | payments + bank | erlang + java | dynamo + oracle | kafka | most interactions are async |
| robinhood  | stock market + bank | python | ...  | kafka | ....  |



### general business processes or ecommerce 

workflows vs event driven architecture
https://www.infoq.com/presentations/event-flow-distributed-systems

BPMN (Business Process Modeling Notation) - used as a common design language amongh sales / business and engineers.
https://www.lucidchart.com/pages/bpmn?a=0#top-info

there is also BPEL, which seem to be legacy


Orchestration vs choreography
https://stackoverflow.com/questions/4127241/orchestration-vs-choreography

