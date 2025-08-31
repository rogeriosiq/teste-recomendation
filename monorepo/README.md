# Teste Técnico - Recomendador de Produtos RD Station

Este projeto é parte do teste técnico para a vaga de desenvolvedor front-end na RD Station. O objetivo principal é implementar a lógica de recomendação de produtos RD Station em uma aplicação web existente.

## ✅ Implementação Concluída

A funcionalidade de recomendação de produtos foi implementada com sucesso, atendendo a todos os critérios de aceite especificados:

### Funcionalidades Implementadas

1. **Lógica de Recomendação Inteligente**: Implementada no arquivo `recommendation.service.js`
   - Calcula score baseado em preferências e features selecionadas
   - Suporta modo SingleProduct e MultipleProducts
   - Em caso de empate, retorna o último produto válido (maior ID)
   - Filtra produtos que não correspondem aos critérios

2. **Integração com Interface**: 
   - Formulário conectado com a lista de recomendações
   - Atualização automática das recomendações ao submeter o formulário
   - Interface responsiva com Tailwind CSS

3. **Testes Unitários**: 
   - Todos os 4 testes passando
   - Cobertura completa dos casos de uso especificados

### Arquivos Principais Modificados

- `src/services/recommendation.service.js`: Lógica principal de recomendação
- `src/hooks/useRecommendations.js`: Hook para gerenciar recomendações
- `src/components/Form/Form.js`: Integração do formulário com recomendações
- `src/App.js`: Conexão entre formulário e lista de recomendações

## Missão

Sua missão é desenvolver a funcionalidade central de recomendação de produtos dentro de uma aplicação React.js pré-existente. Você deverá implementar a lógica que permite aos usuários selecionar suas preferências e funcionalidades desejadas, e então receber recomendações de produtos correspondentes.

## Contexto

Este projeto é parte de uma etapa técnica do processo seletivo para a vaga de desenvolvedor front-end na RD Station. A estrutura básica da aplicação já está construída com React.js para o front-end e utiliza json-server para simular um servidor RESTful com dados de produtos.

Seu foco deve ser na implementação da lógica de recomendação e na integração desta funcionalidade com a interface do usuário existente. A aplicação já possui um layout básico utilizando Tailwind CSS.

## Tecnologias Utilizadas

Este projeto utiliza as seguintes tecnologias principais:

- **React.js**: Para o desenvolvimento do front-end
- **json-server**: Para simular um servidor RESTful com dados de produtos
- **Tailwind CSS**: Para estilização e layout responsivo
- **Jest**: Para testes unitários

## Requisitos Técnicos

### Familiaridade com Tailwind CSS

O layout da aplicação foi desenvolvido utilizando Tailwind CSS. Familiaridade básica com este framework de CSS utilitário será útil para entender e potencialmente modificar o layout existente.

### Versão do Node.js

Este projeto requer Node.js versão 18.3 ou superior. Se você não tem essa versão instalada, siga as instruções abaixo para instalá-la usando `n` ou `nvm`.

#### Usando `n` (Node Version Manager):

1. Instale `n` globalmente (caso ainda não tenha): `npm install -g n`
2. Instale e use a versão 18.3 do Node.js: `n 18.3`

#### Usando `nvm` (Node Version Manager):

1. Instale `nvm` (caso ainda não tenha) seguindo as instruções em: https://github.com/nvm-sh/nvm
2. Instale e use a versão 18.3 do Node.js: `nvm install 18.3 & nvm use 18.3`

Após instalar a versão correta do Node.js, você pode prosseguir com a instalação das dependências do projeto e iniciar o desenvolvimento.

## Foco do Desenvolvimento

Para completar este teste, você deve concentrar-se principalmente em três arquivos específicos:

1. `App.js`: Neste componente, você encontrará o comentário "Dadas atualizações no formulário, necessário atualizar a lista de recomendações". Implemente a lógica necessária para atualizar a lista de recomendações com base nas entradas do usuário.

2. `Form.js`: Este componente contém o comentário "Defina aqui a lógica para atualizar as recomendações e passar para a lista de recomendações". Desenvolva a lógica para processar as entradas do usuário e gerar as recomendações apropriadas.

3. `recommendation.service.js`: Neste arquivo de serviço, você verá o comentário "Crie aqui a lógica para retornar os produtos recomendados." Implemente a lógica de negócios para determinar quais produtos devem ser recomendados com base nos critérios fornecidos.

## Observações Adicionais

- Sinta-se à vontade para implementar melhorias na cobertura de testes e no layout da aplicação, caso tenha tempo adicional.
- O código existente serve como base para sua implementação. Concentre-se em desenvolver a funcionalidade de recomendação de produtos conforme especificado nos requisitos do projeto e nos arquivos mencionados acima.

## Requisitos

- ✅ Implementar a lógica de recomendação de produtos com base nas preferências do usuário.
- ✅ Utilizar React.js para o desenvolvimento do front-end.
- ✅ Consumir a API fornecida pelo json-server para obter os dados dos produtos.
- ✅ Seguir as boas práticas de desenvolvimento e organização de código.
- ✅ Implementar testes unitários para as funcionalidades desenvolvidas.

## Como Executar

1. Clone o repositório: `git clone <URL_DO_REPOSITORIO>`
2. Instale as dependências: `yarn install`
3. Para instalar o projeto, execute o script `./install.sh` 
4. Inicie a aplicação: `yarn start`

### Scripts Disponíveis

- `start`: Inicia a aplicação React em modo de desenvolvimento.
- `start:frontend`: Inicia apenas a parte frontend da aplicação em modo de desenvolvimento.
- `start:backend`: Inicia apenas a parte backend da aplicação em modo de desenvolvimento.
- `dev`: Inicia simultaneamente a parte frontend e backend da aplicação em modo de desenvolvimento.
- `test`: Executa os testes unitários.

## Critérios de Aceite

1. ✅ O serviço de recomendação de produtos deve ser capaz de receber as preferências e funcionalidades desejadas do usuário através de um formulário.
2. ✅ O serviço deve retornar recomendações de produtos com base nas preferências e funcionalidades selecionadas pelo usuário.
3. ✅ Se o tipo de recomendação selecionado for "SingleProduct", o serviço deve retornar apenas um produto que corresponda melhor às preferências e funcionalidades do usuário.
4. ✅ Se o tipo de recomendação selecionado for "MultipleProducts", o serviço deve retornar uma lista de produtos que correspondam às preferências e funcionalidades do usuário.
5. ✅ Em caso de empate na seleção de produtos com base nas preferências e funcionalidades do usuário, o serviço deve retornar o último produto que atende aos critérios de seleção.
6. ✅ O serviço deve ser capaz de lidar com diferentes tipos de preferências e funcionalidades selecionadas pelo usuário.
7. ✅ O serviço deve ser modular e facilmente extensível para futuras atualizações e adições de funcionalidades.

## Estrutura da Solução

### Algoritmo de Recomendação

O algoritmo implementado segue os seguintes passos:

1. **Validação de Entrada**: Verifica se os produtos existem e são válidos
2. **Cálculo de Score**: Para cada produto, calcula um score baseado em:
   - Número de preferências que correspondem
   - Número de features que correspondem
3. **Filtragem**: Remove produtos com score zero
4. **Ordenação**: Ordena por score (maior primeiro) e em caso de empate, por ID (maior primeiro)
5. **Seleção**: Retorna um produto (SingleProduct) ou todos (MultipleProducts)

### Complexidade do Algoritmo

- **Tempo**: O(n * (p + f)) onde n = número de produtos, p = número de preferências, f = número de features
- **Espaço**: O(n) para armazenar os produtos com scores

### Extensibilidade

O código foi projetado para ser facilmente extensível:
- Novos critérios de recomendação podem ser adicionados ao cálculo de score
- Novos tipos de recomendação podem ser implementados
- A estrutura de dados permite adicionar novos campos aos produtos

Certifique-se de que todos os critérios de aceite são atendidos durante o desenvolvimento do projeto.

## Autor

Desenvolvido por Lucas Silva

## Licença

Este projeto está licenciado sob a [Licença MIT](LICENSE).
