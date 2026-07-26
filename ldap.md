# 1. Teste de LDAP (Autenticação)

Um problema recorrente na empresa era a falha de autenticação dos usuários nos sistemas corporativos. Em praticamente todos os incidentes, a responsabilidade era inicialmente atribuída à equipe de Infraestrutura.

Para investigar a causa, foi realizado um experimento de Chaos Engineering simulando a indisponibilidade do serviço LDAP de uma região. O objetivo era validar se o ambiente possuía mecanismos de redundância e failover capazes de redirecionar automaticamente as requisições para outras regiões.

Durante o teste, foi identificado que, quando o serviço LDAP de uma região ficava indisponível, a comunicação era interrompida e **não ocorria o redirecionamento automático para os servidores redundantes**, tornando indisponível a autenticação dos usuários.

O experimento demonstrou que a solução de alta disponibilidade havia sido implementada, porém **nunca havia sido validada em um cenário real de falha**. A partir dos resultados obtidos, foi possível corrigir a configuração de failover, garantindo que as requisições passassem a ser direcionadas corretamente para outras regiões e aumentando significativamente a resiliência do serviço de autenticação.

**Resultados alcançados:**

* Identificação de uma falha crítica no mecanismo de failover do LDAP.
* Validação da arquitetura de alta disponibilidade.
* Correção do processo de redirecionamento entre regiões.
* Redução do risco de indisisponibilidade para os usuários.
* Maior confiabilidade na infraestrutura de autenticação corporativa.


