# Clean Architecture

Software architecture refers to the high-level structure of a software system. It encompasses the key design decisions, components, interactions, and patterns that shape the system.

#### Different Aspects of Software Architecture

* **System-Level Architecture**:
  * This includes the overall structure of the entire software system.
  * It defines how different components (modules, services, etc.) interact and collaborate.
  * Examples: **Monolithic**, **Microservices**, **Client-Server**, **Event-Driven**, etc.
* **Component-Level Architecture**:
  * Focuses on the organization and relationships among individual components within a module or service.
  * Examples: **Clean Architecture**, **Hexagonal Architecture**, **Layered Architecture**, etc.

The diversity of names reflects the **context**, **focus**, and **granularity** of architectural decisions.

**Clean Architecture** emphasizes code organization and separation of concerns, while **Microservices** focuses on independent deployable units. Each name highlights a specific aspect of the architecture, but they all contribute to the overall system design.

**Software system element**

It is member of a set of elements that constitute a software system.

Note 1 to entry: A software system element can include one or more software units, software elements, hardware units, hardware elements, services, and other system elements and systems.

Note 2 to entry: A software system element can be viewed as a system element.

**Software unit**

It is an atomic‐level software component of the software architecture that can be subjected to standalone testing

Note 1 to entry: Some software units are separately compilable pieces of code

There is another definition: Architecture styles define how different components of an application programming interface (API) interact with one another ([https://blog.bytebytego.com/p/ep56-system-design-blueprint-the](https://blog.bytebytego.com/p/ep56-system-design-blueprint-the)).





### O que é Arquitetura?

De acordo com Bass, Clements e Kazman (2021, p. 29, tradução nossa) “A arquitetura de software é o conjunto de **estruturas necessárias para compreender sobre um sistema**. Essas estruturas abrangem elementos de software, como esses elementos se relacionam, e sobre as suas propriedades”. Por consequência, a partir da definição de Bass, Clements e Kazman (2021),  conclui-se que todo sistema de software possui uma arquitetura, uma vez que sistemas são constituídos de elementos e relacionamentos.

Bass, Clements e Kazman (2021) complementam a definição de arquitetura afirmando que a compreensão ocorre através da abstração do sistema que se dá por meio da **exposição de certos detalhes e ocultação de outros**.

Richardson (2018) afirma que a arquitetura de um sistema é sua **representação em alto nível**, consistindo de estruturas e dependências entre essas estruturas. Ambos os autores, Richardson (2018) e Bass, Clements e Kazman (2021), afirmam que a organização dos componentes que compõem a arquitetura colabora para se atingir atributos de qualidades como confiabilidade, escalabilidade e segurança.

Bass, Clements e Kazman (2021) definem o objetivo da arquitetura como sendo o de dar suporte para construção de um sistema visando atender os objetivos do negócio. Dessa forma, o grande propósito das decisões arquiteturais é cumprir com os requisitos funcionais e atributos de qualidade estipulados pelo negócio e stakeholders.

Robert C. Martin, reuniu uma série de técnicas, princípios e conceitos e cunhou o termo Clean Architecture para definir um padrão de arquitetura para estruturar e organizar sistemas de software de tal modo que as regras de negócio sejam os elementos centrais, ao mesmo tempo em que torna os detalhes “irrelevantes” perante essas regras \[1].



### Clean Architecture

Os sistemas de software podem ser decompostos em dois elementos principais: políticas e detalhes \[1]. Os elementos relacionados à política incorporam todas as regras de negócio, são neles onde o verdadeiro valor do sistema reside.

Os detalhes são os facilitadores e habilitadores necessários para que o sistema consiga atingir seu objetivo, mas estes não impactam ou possuem efeito sobre elementos da regra de negócios.

O propósito da arquitetura é criar e estabelecer as formas do sistema, de tal modo que as regras de negócio sejam os elementos centrais, ao mesmo tempo em que torna os detalhes “irrelevantes” perante essas regras \[1].

Um dos maiores benefícios que se pode alcançar ao seguir essa abordagem arquitetural é o desenvolvimento das políticas de alto nível sem se comprometer com os detalhes que as cercam. Fazendo isso, é possível adiar decisões sobre os detalhes por um período maior de tempo e, quanto mais no futuro essas decisões forem tomadas, mais informações existirão para ajudar no processo de tomada de decisão \[1].

Robert C. Martin, reuniu uma série de técnicas, princípios e conceitos e cunhou o termo Clean Architecture para definir um padrão de arquitetura para estruturar e organizar sistemas de software a fim de satisfazer os aspectos que arquiteturas de sistemas necessitam cumprir.

Clean Architecture utiliza uma estrutura em camadas, similar a estrutura definida por Jeffrey Palermo em Onion Architecture \[2]. Os componentes definidos nas camadas externas dependem dos componentes definidos nas camadas internas, mas não o contrário \[5].&#x20;

A base para o modelo de arquitetura proposto por Robert C. Martin são algumas das regras e princípios listados abaixo:&#x20;

* Regra da Dependência (Dependency Rule), que descreve a ideia de que as relação de dependência entre os elementos do sistema só podem apontar para o centro da arquitetura, local onde residem os as regras de neǵocio;
* Princípio de Inversão de Dependência (Dependency Inversion Principle), que afirma que módulos de alto nível não devem depender de módulos de baixo nível. Ambos devem depender de abstrações;
* Princípio de abstrações estáveis (Stable Abstractions Principle); os componentes estáveis ​​devem ser abstratos. Um possível exemplo de um componente estável e abstrato é uma política de alto nível que é alterada por extensão seguindo o open-closed principle \[1];
* Princípio da Responsabilidade Única (Single Responsibility Principle), que descreve a ideia de que uma classe deve ter um, e apenas um, motivo para mudar;
* Princípio Comum de Fechamento (Common Closure Principle), que afirma que classes que mudam juntas devem ser agrupadas;
* Arquitetura Ports and Adapters de Alistair Cockburn, para estabelecer comunicação entre as camadas \[6]. As portas representam os limites entre as camadas. Os adaptadores são, essencialmente, a implementação das portas. Essa arquitetura visa mitigar o acoplamento entre as camadas \[6].



<figure><img src="https://lh7-us.googleusercontent.com/JWSpfPb0LUvEbMnoqlYExyQUFRKNAJLvDrjMbnU92gtl3PEayB1CNm-iRkIFtBABCfa316LN7TckKWayC9RBNHqzH_0TDFlxbOXoVDK7fFdHBJqoVfR5620oOrsml9ah4SOUDoVvr_3Mgy_gj65wug" alt=""><figcaption><p>Figura. 1. Camadas estabelecidas em Clean Architecture e sua orientação para dentro dependências [2].</p></figcaption></figure>

\
A Figura 1 ilustra as camadas principais do _Clean Architecture._ Essas camadas são:

* Entidades (_Entities_): Camada responsável por conter e encapsular as regras críticas de negócio de toda a organização.&#x20;
* Casos de Uso (_Use Cases_): Camada responsável por conter regras de negócio específicas da aplicação. Essa camada encapsula e implementa os casos de uso do sistema \[2], e realiza a manipulação e controle do fluxo de dados que entra e saí da camada de entidade \[1].
* Interfaces e Adaptadores (_Interface e Adaptors_):  Camada intermediária que estabelece os limites entre Use Cases e camadas externas, além de servir de conversor dos dados que circulam entre as camadas.
* _Frameworks_ e _Drivers_: Camada onde os “detalhes” habilitadores do funcionamento do sistema são inseridos. Exemplo: Banco de dados, _Frameworks_ Web e UI.
