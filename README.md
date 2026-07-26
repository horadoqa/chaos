# Chaos Testing (ou Chaos Engineering)

**Chaos Testing** (ou **Chaos Engineering**) é uma prática de testes que consiste em provocar falhas controladas em um sistema para avaliar sua capacidade de continuar funcionando, recuperar-se rapidamente e manter a disponibilidade. Em vez de assumir que tudo funcionará perfeitamente, essa abordagem parte do princípio de que falhas são inevitáveis em ambientes distribuídos e devem ser testadas antes que ocorram em produção.

## Objetivo

O principal objetivo do Chaos Testing é aumentar a **resiliência** dos sistemas, identificando pontos fracos antes que eles causem interrupções para os usuários. A prática ajuda as equipes a responder perguntas como:

* O sistema continua disponível se um servidor falhar?
* Como a aplicação reage à perda de conexão com o banco de dados?
* O balanceador de carga distribui corretamente o tráfego quando uma instância fica indisponível?
* Os mecanismos de recuperação automática funcionam como esperado?

## Como funciona

Um experimento de Chaos Testing normalmente segue estas etapas:

1. **Definir o estado normal do sistema**

   * Identificar métricas como tempo de resposta, taxa de erros, uso de CPU e disponibilidade.

2. **Criar uma hipótese**

   * Exemplo: "Se um dos servidores da aplicação falhar, o sistema continuará atendendo às requisições sem impacto significativo."

3. **Introduzir uma falha controlada**

   * Desligar uma instância.
   * Simular alta latência.
   * Interromper a comunicação com um serviço.
   * Limitar recursos como CPU ou memória.

4. **Monitorar os resultados**

   * Observar métricas, logs, alarmes e comportamento da aplicação.

5. **Analisar e corrigir vulnerabilidades**

   * Implementar melhorias para tornar o sistema mais resistente.

## Exemplos de falhas simuladas

* Queda de servidores.
* Falha de rede.
* Perda de conexão com banco de dados.
* Aumento artificial da latência.
* Timeout entre microsserviços.
* Consumo excessivo de CPU.
* Falta de memória.
* Erros em APIs externas.
* Interrupção de filas de mensagens.
* Falhas em provedores de armazenamento.

## Benefícios

* Maior confiabilidade dos sistemas.
* Identificação precoce de falhas.
* Validação de mecanismos de recuperação.
* Redução do tempo de indisponibilidade.
* Maior confiança em implantações em produção.
* Melhoria contínua da arquitetura.

## Riscos

Se executado sem planejamento, o Chaos Testing pode causar impactos reais nos usuários. Por isso, recomenda-se:

* Executar inicialmente em ambientes de teste ou homologação.
* Utilizar experimentos pequenos e controlados.
* Definir critérios claros para interromper o experimento.
* Monitorar continuamente os indicadores do sistema.
* Ter planos de rollback e recuperação.

## Ferramentas populares

Algumas ferramentas amplamente utilizadas são:

* **Chaos Monkey** – Simula falhas desligando instâncias automaticamente.
* **LitmusChaos** – Plataforma para Kubernetes com diversos tipos de experimentos.
* **Gremlin** – Solução comercial para experimentos de caos.
* **Chaos Mesh** – Ferramenta de Chaos Engineering para ambientes Kubernetes.
* **PowerfulSeal** – Focada em testes de resiliência em clusters Kubernetes.

## Exemplo prático

Imagine uma aplicação de comércio eletrônico composta por vários microsserviços:

* Serviço de autenticação
* Serviço de catálogo
* Serviço de pagamento
* Banco de dados
* Cache

Um teste de caos pode desligar propositalmente uma instância do serviço de catálogo durante um período de baixo tráfego. O objetivo é verificar se:

* O balanceador redireciona as requisições para outra instância.
* Os usuários continuam navegando normalmente.
* Alertas são disparados automaticamente.
* O sistema recupera a instância sem intervenção manual.

Se a aplicação continuar funcionando com impacto mínimo, isso indica que sua arquitetura possui um bom nível de resiliência.

## Boas práticas

* Começar com experimentos simples.
* Automatizar os testes no pipeline de integração e entrega contínuas (CI/CD).
* Executar durante períodos de menor risco.
* Definir métricas de sucesso antes do experimento.
* Documentar os resultados e as ações corretivas.
* Evoluir gradualmente a complexidade dos cenários de falha.

## Conclusão

Chaos Testing é uma abordagem proativa para validar a robustez de sistemas, especialmente em arquiteturas distribuídas e baseadas em microsserviços. Ao simular falhas de forma controlada, as equipes conseguem identificar vulnerabilidades, fortalecer mecanismos de recuperação e aumentar a confiabilidade dos serviços antes que problemas reais afetem os usuários. Essa prática é hoje considerada um componente importante das estratégias de engenharia de confiabilidade (SRE) e de operações modernas em nuvem.
