# fintech_resources
Curated list of Fintech resources


## Podcasts

1. Starling developer podcast (https://itunes.apple.com/us/podcast/starling-developer-podcast/id1274198025?mt=2)


### Specific podcast episodes

talks

#### uber
https://www.youtube.com/watch?v=Dz6dAZs8Scg
https://www.youtube.com/watch?v=XzJDNg_iSaA

#### stripe
https://www.infoq.com/presentations/stripe-api-pci

#### netflix
https://youtu.be/sYFDnGjNVrk?t=120

#### N26
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

#### robinhood
https://www.youtube.com/watch?v=RVr3NldzmcY&t=3s

5. nubank
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


klarna
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
