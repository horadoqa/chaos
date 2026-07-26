# Testes de Chaos Engineering realizados

**1. Teste de LDAP (Autenticação)**

**Objetivo:**
Validar a resiliência do serviço de autenticação, verificando se os usuários conseguiriam acessar os sistemas corporativos caso o serviço LDAP de uma determinada região ficasse indisponível.

**Cenário simulado:**
Foi induzida a indisponibilidade do serviço LDAP em uma região específica para avaliar o comportamento dos mecanismos de redundância e failover.

**Validações realizadas:**

* Continuidade da autenticação dos usuários.
* Funcionamento do failover para servidores LDAP redundantes.
* Disponibilidade dos sistemas corporativos durante a falha.
* Integridade das permissões e autenticação após a recuperação do serviço.

**Resultado esperado:**
Os usuários deveriam continuar realizando login normalmente, utilizando a infraestrutura redundante, sem impacto significativo na disponibilidade dos sistemas.

---

**2. Teste de DNS (Resolução de nomes)**

**Objetivo:**
Validar a continuidade da resolução de nomes e da comunicação entre aplicações diante da indisponibilidade de um servidor ou serviço DNS.

**Cenário simulado:**
Foi provocada a indisponibilidade de um servidor DNS para verificar a capacidade de recuperação e redundância da infraestrutura.

**Validações realizadas:**

* Funcionamento dos servidores DNS secundários.
* Continuidade da resolução de nomes internos e externos.
* Disponibilidade das aplicações dependentes de DNS.
* Tempo de recuperação (RTO) e impacto para os usuários.

**Resultado esperado:**
As consultas DNS deveriam ser automaticamente direcionadas aos servidores redundantes, mantendo a disponibilidade das aplicações e minimizando impactos operacionais.

### Relação com Chaos Engineering

Ambos os testes seguem os princípios de Chaos Engineering, pois consistem na introdução controlada de falhas em componentes críticos da infraestrutura (LDAP e DNS) para validar a resiliência do ambiente, os mecanismos de alta disponibilidade, o failover e a continuidade dos serviços. Em vez de apenas verificar se os componentes funcionam normalmente, esses experimentos avaliam como o ambiente se comporta quando ocorre uma falha real, permitindo identificar vulnerabilidades e aprimorar a confiabilidade da infraestrutura.
