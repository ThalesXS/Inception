# O Que é o Docker?

Docker é uma ferramenta que permite aos desenvolvedores, _sys-admins_, etc, implantar (_deploy_) aplicações em uma _sandbox_ conhecida como _container_ para correr no systema operacional do host (e.g., Linus, McOS, Windows). O principal benefício de um Docker é que ele permite aos usuários "empacotar" uma aplicação com todas suas dependências em uma unidade padronizada para desenvolvimento de software. Diferente das _[[Virtual Machine|Virtual Machines]]_, _containers_ não possuem uma sobrecarga alta, o que permite um uso mais eficiente do sistema e recursos subjacentes.

## O que são _Containers_?

O padrão atualmente é usar Virtual Machines (VMs) para correr aplicações de software. As VMs correm as aplicações dentro de um sistema operacional, o qual roda dentro de um _hardware virtual_ alimentada pelo Sistema Operacional do Host do servidor.

VMs são ótimas em fornecer um isolamento completo de processos para aplicações: Existem poucas maneiras em que um problema no sistema operacional do host pode afetar o software correndo dentro do sistema operacional da VM, e vice-versa. Porém, esse isolamento vem ao custo da alta sobrecarga computacional gasta na virtualização para o Sistema Operacional "hospede" é substancial.

_Containers_, por outro lado, se aproveitam das mecânicas de baixo nível do Sistema Operacional "anfitrião" para fornecer grande parte do isolamento das VMs com uma fração do poder computacional.

## Porquê usar _containers_?

Containers oferecem um mecanismo de empacotamento lógico no qual aplicações podem ser abstraídas do ambiente no qual elas correm. Essa dissociação permite que aplicações baseadas em containers sejam facilmente e consistentemente implementadas, independente de se o ambiente alvo é um _data center_ privado, uma _cloud_ pública, ou até o laptop pessoal de um desenvolvedor. Isso concede a desenvolvedores a habilidade de criar ambientes previsíveis que são isoladas do resto das aplicações e podem ser corridas em qualquer lugar.

De um ponto de vista operacional, além da portabilidade, containers também concedem mais controle granular[^1] sobre recursos, concedendo a infraestrutura maior eficiência, o que pode resultar em um uso otimizado dos recursos de computação.

Por conta desses benefícios, os _containers_ (e Docker) tem sido cada vez mais adotados. Empresas como google, Facebook, Netflix e Salesforce, aproveitam-se dos _containers_ para melhorar a produtividade em grandes grupos de engenheiros, e para melhorar a utilização dos recursos de computação.



[^1]: Habilidade de especificar detalhes e permissões de acesso específicas para diferentes grupos ou usuários.