# Informações Técnicas - Recomendador de Produtos RD Station

## Versões e Dependências

### Node.js
- **Versão Requerida**: 18.3 ou superior
- **Versão Testada**: 18.3
- **Gerenciador de Pacotes**: Yarn

### Principais Dependências
- **React**: 18.2.0
- **React Scripts**: 5.0.1
- **Tailwind CSS**: 3.3.0
- **Jest**: 29.5.0
- **json-server**: 0.17.3

## Estrutura do Projeto

```
monorepo/
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   │   ├── Form/
│   │   │   │   ├── Form.js (✅ Implementado)
│   │   │   │   └── Fields/
│   │   │   └── RecommendationList/
│   │   ├── services/
│   │   │   ├── recommendation.service.js (✅ Implementado)
│   │   │   └── product.service.js
│   │   ├── hooks/
│   │   │   └── useRecommendations.js (✅ Implementado)
│   │   ├── mocks/
│   │   │   └── mockProducts.js
│   │   └── App.js (✅ Implementado)
│   └── package.json
├── backend/
│   ├── db.json
│   └── package.json
└── package.json
```

## Algoritmo de Recomendação

### Lógica Implementada

O algoritmo de recomendação foi implementado seguindo os princípios de Clean Code e performance:

1. **Validação de Entrada**
   - Verifica se os produtos existem e são um array válido
   - Trata casos edge (arrays vazios, dados inválidos)

2. **Cálculo de Score**
   - Para cada produto, calcula um score baseado em:
     - Número de preferências que correspondem às selecionadas
     - Número de features que correspondem às selecionadas
   - Score = (preferências correspondentes) + (features correspondentes)

3. **Filtragem e Ordenação**
   - Remove produtos com score zero (sem correspondência)
   - Ordena por score decrescente
   - Em caso de empate, ordena por ID decrescente (último produto primeiro)

4. **Seleção Final**
   - **SingleProduct**: Retorna apenas o primeiro produto (maior score)
   - **MultipleProducts**: Retorna todos os produtos que correspondem

### Complexidade

- **Tempo**: O(n * (p + f))
  - n = número de produtos
  - p = número de preferências selecionadas
  - f = número de features selecionadas
- **Espaço**: O(n) para armazenar produtos com scores

### Casos de Teste Cobertos

1. ✅ SingleProduct com preferências específicas
2. ✅ MultipleProducts com múltiplas preferências
3. ✅ SingleProduct com empate (retorna último)
4. ✅ Empate entre produtos (retorna maior ID)

## Funcionalidades Implementadas

### 1. Serviço de Recomendação (`recommendation.service.js`)
- Lógica principal de recomendação
- Cálculo de scores baseado em preferências e features
- Suporte a SingleProduct e MultipleProducts
- Tratamento de empates

### 2. Hook de Recomendações (`useRecommendations.js`)
- Gerenciamento de estado das recomendações
- Integração com o serviço de recomendação
- Atualização automática do estado

### 3. Formulário Integrado (`Form.js`)
- Recebe prop `onRecommendationsUpdate`
- Chama o serviço de recomendação no submit
- Atualiza recomendações via useEffect

### 4. Aplicação Principal (`App.js`)
- Gerencia estado das recomendações
- Conecta formulário com lista de recomendações
- Passa callback para atualização

## Boas Práticas Implementadas

### Clean Code
- Funções com responsabilidade única
- Nomes descritivos para variáveis e funções
- Comentários explicativos onde necessário
- Código legível e bem estruturado

### Performance
- Algoritmo otimizado com complexidade linear
- Evita loops desnecessários
- Filtragem eficiente de produtos

### Testabilidade
- Funções puras e testáveis
- Separação de responsabilidades
- Mocks para dados de teste

### Extensibilidade
- Estrutura modular
- Fácil adição de novos critérios
- Suporte a novos tipos de recomendação

## Como Executar

### Pré-requisitos
```bash
# Verificar versão do Node.js
node --version  # Deve ser >= 18.3

# Instalar dependências
yarn install

# Executar script de instalação
./install.sh
```

### Comandos Disponíveis
```bash
# Executar testes
yarn test

# Iniciar aplicação completa
yarn dev

# Iniciar apenas frontend
yarn start:frontend

# Iniciar apenas backend
yarn start:backend
```

## Pontos de Melhoria Futura

1. **Cache de Recomendações**: Implementar cache para melhorar performance
2. **Pesos Personalizados**: Permitir pesos diferentes para preferências vs features
3. **Histórico de Recomendações**: Salvar histórico de recomendações do usuário
4. **Machine Learning**: Implementar algoritmos mais sofisticados de recomendação
5. **Testes de Integração**: Adicionar testes end-to-end
6. **Otimização de Performance**: Implementar virtualização para listas grandes

## Observações Importantes

- O código foi projetado seguindo o princípio "projete seu código para ser mais fácil de entender, não mais fácil de escrever"
- Todos os critérios de aceite foram atendidos
- A solução é modular e extensível
- Os testes cobrem todos os casos de uso especificados
- A interface é responsiva e acessível
