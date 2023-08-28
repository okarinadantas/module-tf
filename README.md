
# Guia Básico para Criação de Módulos no Terraform


Este guia tem como objetivo fornecer uma visão geral simples sobre a criação de módulos no Terraform, uma ferramenta de infraestrutura como código (IaC) que permite gerenciar recursos de infraestrutura em várias nuvens de forma automatizada e consistente.

## O que são Módulos no Terraform?

Os módulos no Terraform são blocos reutilizáveis de configuração que encapsulam um conjunto específico de recursos ou funcionalidades. Eles permitem organizar e compartilhar a lógica de infraestrutura de maneira modular, promovendo a reutilização e a manutenção simplificada.


## Estrutura Básica de um Módulo




```
  mymodule/
│
├── main.tf
├── variables.tf
├── outputs.tf
└── README.md
```

- main.tf: Este arquivo contém a definição dos recursos e configurações específicas do módulo.

- variables.tf: Aqui, você define as variáveis de entrada que o módulo aceitará. Isso permite que você personalize o comportamento do módulo ao usá-lo.

- outputs.tf: Neste arquivo, você define as saídas do módulo - valores que podem ser acessados após a implantação para obter informações geradas pelo módulo.

- README.md: Um arquivo de documentação que explica como usar o módulo, quais são suas entradas e saídas, exemplos de uso e quaisquer outras informações relevantes.


## Como Usar um Módulo

- Crie ou vá para o diretório do seu projeto onde você deseja usar o módulo.

- Crie um arquivo main.tf: Neste arquivo, você configura os recursos principais usando o módulo. Importe o módulo usando a seguinte sintaxe:

```
module "nome_qualquer" {
  source = "./caminho_para_o_modulo"
  
  // Defina as variáveis do módulo, se necessário
  var_name = valor
}
```

- Defina as variáveis do módulo: As variáveis do módulo podem ser definidas no mesmo arquivo ou em um arquivo separado, como variables.tf.

- Acesse as saídas do módulo: Você pode acessar as saídas definidas no módulo da seguinte forma:

```
output "nome_saida" {
  value = module.nome_qualquer.nome_saida
}
```

#### Execute os comandos do Terraform:

- terraform init: Inicialize o projeto.
- terraform apply: Implante os recursos.
- terraform destroy: Remova os recursos, se necessário.
