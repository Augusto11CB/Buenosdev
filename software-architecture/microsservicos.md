# Microsserviços

Neste artigo, daremos continuidade à nossa discussão sobre arquitetura de software, com foco na arquitetura de microsserviços. Além disso, exploraremos seus princípios fundamentais, bem como os benefícios e desvantagens associados a essa abordagem.



### 1 . Arquitetura de Microsserviços

A arquitetura de microsserviços estrutura um sistema como um conjunto de microsserviços com escopo bem definido, fracamente acoplados, independentes e que implementam uma funcionalidade ou operações específicas do negócio (RICHARDSON, 2018).&#x20;

Esta arquitetura de software foi projetada para acelerar os ciclos de desenvolvimento e implantação, promover a inovação, melhorar a capacidade de manutenção e a escalabilidade do software. Além disso, ela contribui positivamente com diversos aspectos sistêmicos como testabilidade, capacidade de manutenção, escalabilidade e melhoria nos ciclos de desenvolvimento e implantação. Assim sendo, como um dos efeitos de sua utilização, é proporcionada à organização que emprega esse tipo de arquitetura o desenvolvimento de software com mais qualidade e rapidez (RICHARDSON, 2018 e FARSI et al., 2021).

O microsserviço é um componente de software independente que provê funcionalidades através de comandos, consultas (queries) e eventos por meio de APIs e sistemas de mensageria (como por exemplo Apache Kafka e RabbitMQ). Nesta arquitetura, APIs possuem um papel vital, pois através delas há a exposição de funcionalidades e, também, há a exposição de operações que suportam a colaboração entre os demais componentes da arquitetura para realizar os workflows de negócio (RICHARDSON, 2018).&#x20;

A Figura 4 mostra uma organização típica de uma arquitetura de microsserviços. Vários microsserviços compõem o sistema, cada um exercendo uma função específica. Cada microsserviço possui seu próprio banco de dados e se relacionam uns com os outros através de APIs REST ou filas provenientes de sistemas de mensageria. As requisições de clientes são feitas para um API-Gateway que é responsável por redirecionar a requisição para o microsserviço correto.

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption><p>Figura 4 – Exemplo de uma arquitetura de microsserviços.<br>Fonte: (RICHARDS; FORD, 2020), adaptado pelo Autor.</p></figcaption></figure>
