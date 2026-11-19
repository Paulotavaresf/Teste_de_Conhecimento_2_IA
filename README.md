# Implementação de uma Rede Neural Artificial Já Treinada

**Disciplina:** Matemática Computacional  
**Professor:** Prof. Dr. Alexsandro O. A.

## 1. Sobre o Projeto

Este projeto consiste na implementação de uma rede neural artificial previamente treinada, utilizando Python e NumPy, com o objetivo de realizar a propagação direta (*Forward Pass*) para classificação de modalidades de envio de encomendas.

A rede recebe quatro características de uma entrega e, por meio de operações matemáticas com matrizes, vetores, pesos, vieses e funções de ativação, calcula as probabilidades de cada modalidade de envio.

O objetivo é compreender e implementar o funcionamento interno de uma rede neural, sem utilizar bibliotecas especializadas de aprendizado de máquina.

## 2. Objetivos

- Implementar a propagação direta de uma rede neural do zero.
- Trabalhar com multiplicação de matrizes por vetores.
- Aplicar funções de ativação ReLU, tanh e Softmax.
- Realizar a normalização dos dados de entrada.
- Calcular as probabilidades de classificação.
- Validar os resultados utilizando um exemplo previamente resolvido.
- Avaliar o desempenho da rede em um conjunto de 10 entregas.

## 3. Tecnologias Utilizadas

- **Python:** linguagem utilizada no desenvolvimento.
- **NumPy:** operações matemáticas com matrizes e vetores.
- **Pandas:** leitura e manipulação dos dados em formato CSV.
- **JSON:** armazenamento da arquitetura, dos pesos, vieses e divisores de normalização.

Não foram utilizadas bibliotecas prontas de redes neurais, como TensorFlow, PyTorch, Keras ou Scikit-learn.

## 4. Estrutura da Rede Neural

A rede neural possui quatro camadas, sendo uma camada de entrada, duas camadas ocultas e uma camada de saída.

| Camada | Neurônios | Função de ativação |
|---|---:|---|
| Entrada | 4 | Nenhuma |
| Oculta 1 | 6 | ReLU |
| Oculta 2 | 4 | tanh |
| Saída | 3 | Softmax |

### Características de entrada

Cada entrega é representada por quatro atributos:

- `distancia_km`: distância entre origem e destino.
- `peso_kg`: peso da encomenda.
- `urgencia`: nível de urgência.
- `valor_declarado`: valor declarado da encomenda.

Antes de serem processados pela rede, os atributos passam por uma etapa de normalização, na qual cada valor é dividido pelo seu respectivo divisor.

### Classes de saída

A rede realiza a classificação em três modalidades:

1. PAC;
2. SEDEX;
3. SEDEX 10.

A classe com a maior probabilidade calculada é considerada a previsão final da rede.

## 5. Funcionamento da Propagação Direta

O processamento ocorre em três etapas principais:

**Primeira camada oculta — ReLU**

Realiza a multiplicação da matriz de pesos pela entrada, adiciona o vetor de viés e aplica a função ReLU.

**Segunda camada oculta — tanh**

Recebe os resultados da primeira camada, realiza novas operações matriciais e aplica a função de ativação tanh.

**Camada de saída — Softmax**

Calcula os valores finais (logits) e utiliza a função Softmax para transformar esses valores em probabilidades, cuja soma é igual a 1.

A classificação é definida pelo índice que apresenta a maior probabilidade.

## 6. Arquivos do Projeto

O repositório está organizado com os seguintes arquivos:

| Arquivo | Descrição |
|---|---|
| `rede_template.py` | Implementação das funções de propagação, classificação e validação. |
| `pesos_rede.json` | Armazena a arquitetura, os pesos, os vieses e os divisores de normalização. |
| `entregas_teste_rede.csv` | Contém as 10 entregas utilizadas para avaliação da rede. |

## 7. Validação da Implementação

Para verificar se a implementação está correta, foi utilizado o exemplo de entrada normalizada:

`x = (0.60, 0.40, 0.50, 0.20)`

Os resultados obtidos são comparados com os valores de referência fornecidos pelo professor.

**Resultado esperado:**

| Classe | Probabilidade |
|---|---:|
| PAC | 0,03% |
| SEDEX | 99,55% |
| SEDEX 10 | 0,42% |

**Classificação prevista:** SEDEX, com aproximadamente 99,55% de probabilidade.

A validação também verifica os valores intermediários de cada camada, garantindo que as operações matemáticas estejam sendo executadas corretamente.

## 8. Avaliação da Rede Neural

Após a validação, a implementação é utilizada para processar as 10 entregas disponibilizadas no arquivo `entregas_teste_rede.csv`.

Nessa etapa, são realizadas as seguintes atividades:

- Leitura dos dados das entregas.
- Normalização dos atributos.
- Propagação dos dados pelas camadas da rede.
- Cálculo das probabilidades de cada modalidade.
- Identificação da classe prevista.
- Comparação entre a modalidade prevista e a modalidade real.

Os resultados permitem avaliar a capacidade de classificação da rede neural no conjunto de dados fornecido.

## 9. Como Executar o Projeto

**Pré-requisitos:**

- Python instalado.
- NumPy instalado.
- Pandas instalado.

Instale as dependências com:

```bash
pip install numpy pandas
```

Coloque os três arquivos do projeto na mesma pasta e execute:

```bash
python rede_template.py
```

O programa realizará a validação da rede e executará os procedimentos de classificação definidos na implementação.

## 10. Considerações Finais

O desenvolvimento deste projeto possibilita compreender, na prática, como uma rede neural artificial realiza o processamento de informações e produz previsões a partir de dados de entrada.

A implementação da propagação direta sem o uso de bibliotecas especializadas permite visualizar a importância das operações matriciais, dos pesos, dos vieses e das funções de ativação no funcionamento de uma rede neural.

Além disso, o exercício demonstra como conceitos de Matemática Computacional podem ser aplicados a um problema real de classificação.

---

**Disciplina:** Matemática Computacional  
**Professor:** Prof. Dr. Alexsandro O. A.