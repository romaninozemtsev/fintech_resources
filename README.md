# fintech_resources
Curated list of Fintech resources


## Podcasts

1. Starling developer podcast (https://itunes.apple.com/us/podcast/starling-developer-podcast/id1274198025?mt=2)


### Specific podcast episodes

talks

1. uber
https://www.youtube.com/watch?v=Dz6dAZs8Scg
https://www.youtube.com/watch?v=XzJDNg_iSaA

2. stripe
https://www.infoq.com/presentations/stripe-api-pci

3. netflix
https://youtu.be/sYFDnGjNVrk?t=120

4. robinhood
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




## Blogs
https://robinhood.engineering/

## Articles
https://medium.com/airbnb-engineering/tracking-the-money-scaling-financial-reporting-at-airbnb-6d742b80f040




