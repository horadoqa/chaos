# 2. Teste de DNS (Resolução de Nomes)

O serviço de DNS é um dos componentes mais críticos da infraestrutura, pois sua indisponibilidade pode impedir a comunicação entre aplicações e tornar diversos serviços inacessíveis, mesmo quando os servidores permanecem operacionais.

Para validar a resiliência desse serviço, foi realizado um experimento de Chaos Engineering simulando a indisponibilidade de um dos servidores DNS da infraestrutura. O objetivo era verificar se os mecanismos de redundância e failover redirecionariam automaticamente as consultas para os servidores secundários, garantindo a continuidade da resolução de nomes.

Durante o teste, foi possível validar o comportamento da infraestrutura em um cenário real de falha, identificando oportunidades de melhoria nas configurações de redundância e no processo de recuperação automática. Após os ajustes necessários, novos testes confirmaram que as consultas DNS passaram a ser direcionadas corretamente aos servidores redundantes, mantendo a disponibilidade dos serviços.

**Resultados alcançados:**

* Validação do mecanismo de redundância dos servidores DNS.
* Identificação e correção de falhas no processo de failover.
* Garantia da continuidade da resolução de nomes durante indisponibilidades.
* Aumento da disponibilidade e da resiliência dos sistemas dependentes do serviço de DNS.
* Maior confiança na infraestrutura por meio da validação de cenários reais de falha.
