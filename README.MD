# Modelo Oficina Mecânica 🔧
## Descrição do Projeto
Este projeto representa um modelo de banco de dados para um sistema de controle e gerenciamento de ordens de serviço em uma oficina mecânica. A seguir, está uma descrição detalhada de cada entidade e suas relações:

### Cliente
Descrição: Representa os clientes da oficina, contendo informações básicas.
Atributos: idCliente, nome, endereco, telefone.
## Veiculo
Descrição: Contém informações sobre os veículos dos clientes.
Atributos: placa, modelo, ano, idCliente.
Relacionamentos: Cada veículo pertence a um cliente (1
com Cliente).
## Ordem de Servico (OS)
Descrição: Registra as ordens de serviço realizadas na oficina, incluindo detalhes sobre o veículo, equipe responsável e status do serviço.
Atributos: idOS, numOS, dataEmissao, valorTotal, status, dataConclusao, VeiculoPlaca, idEquipe, idCliente.
### Relacionamentos:
Cada OS está associada a um veículo (N:1 com Veiculo).
Cada OS está associada a um cliente (N:1 com Cliente).
Cada OS é gerenciada por uma equipe (N:1 com Equipe).
## Equipe
Descrição: Representa as equipes de mecânicos da oficina.
Atributos: idEquipe, nome.
### Relacionamentos:
Uma equipe pode ter vários mecânicos (1
com Mecanico).
Uma equipe pode ser responsável por várias ordens de serviço (1
com Ordem de Servico).
Uma equipe pode realizar vários serviços (N
com Servico_OS através de Equipe_Servico).
## Mecanico
Descrição: Contém informações sobre os mecânicos que trabalham na oficina.
Atributos: idMecanico, codigo, nome, endereco, especialidade, idEquipe.
### Relacionamentos: Cada mecânico pertence a uma equipe (N:1 com Equipe).
## Servico_OS
Descrição: Relaciona as ordens de serviço com os serviços realizados.
Atributos: idOS, idServico, quantidade.
### Relacionamentos:
Cada registro relaciona uma ordem de serviço com a mão-de-obra necessária (N:1 com Ordem de Servico).
Cada registro relaciona uma ordem de serviço com um tipo específico de mão-de-obra (N:1 com Mao-de-Obra).
## Peca_OS
Descrição: Relaciona as ordens de serviço com as peças utilizadas.
Atributos: idOS, idPeca, quantidade.
### Relacionamentos:
Cada registro relaciona uma ordem de serviço com uma peça específica (N:1 com Ordem de Servico).
Cada registro relaciona uma ordem de serviço com uma peça utilizada (N:1 com Peca).
## Peca
Descrição: Representa as peças disponíveis para os serviços na oficina.
Atributos: idPeca, descricao, valor.
### Relacionamentos: Cada peça pode estar em várias ordens de serviço (1
com Peca_OS).
## Mao-de-Obra
Descrição: Representa os tipos de mão-de-obra disponíveis na oficina.
Atributos: idMO, descricao, valorHora.
### Relacionamentos: Cada tipo de mão-de-obra pode estar associado a várias ordens de serviço (1
com Servico_OS).
## Equipe_Servico
Descrição: Relaciona as equipes com os serviços que elas podem realizar.
Atributos: idEquipe, idServico.
### Relacionamentos:
Cada registro relaciona uma equipe com um serviço específico (N
com Servico_OS).
# Estrutura do Banco de Dados
A estrutura do banco de dados é desenhada para garantir a integridade e a eficiência na gestão das informações de uma oficina mecânica, cobrindo desde o cadastro dos clientes e veículos até a gestão de ordens de serviço, equipes, mecânicos, serviços, peças e mão-de-obra.