### Descrição do Repositório: Classificador MNIST com Rede Neural de 2 Camadas e 128 Neurônios

Este repositório contém uma implementação completa de uma rede neural de duas camadas, projetada para classificar dígitos manuscritos do conjunto de dados MNIST. A rede é composta por uma camada oculta com 128 neurônios e utiliza as funções de ativação ReLU e Softmax. O modelo é treinado usando a técnica de backpropagation com a função de perda de entropia cruzada.

#### Funções Implementadas:

1. **`relu(x)`**:
   - **Descrição**: Calcula a função de ativação ReLU, que introduz não-linearidade ao modelo. ReLU é definida como max(0, x).
   - **Parâmetros**:
     - `x`: Array NumPy com os valores de entrada.

2. **`relu_derivative(x)`**:
   - **Descrição**: Calcula a derivada da função ReLU, utilizada no processo de backpropagation.
   - **Parâmetros**:
     - `x`: Array NumPy com os valores de entrada.

3. **`softmax(x)`**:
   - **Descrição**: Aplica a função de ativação Softmax, que é usada na última camada de redes neurais para classificação multiclasse. Essa função normaliza as saídas em uma distribuição de probabilidade.
   - **Parâmetros**:
     - `x`: Array NumPy com os valores de entrada.

4. **`cross_entropy_loss(predictions, targets)`**:
   - **Descrição**: Calcula a perda de entropia cruzada, uma métrica de perda comum para problemas de classificação.
   - **Parâmetros**:
     - `predictions`: Previsões do modelo.
     - `targets`: Rótulos verdadeiros.

5. **`predict(x, W1, b1, W2, b2)`**:
   - **Descrição**: Realiza a predição usando os parâmetros da rede. Passa os dados de entrada pela rede para obter as previsões.
   - **Parâmetros**:
     - `x`: Dados de entrada.
     - `W1, b1, W2, b2`: Pesos e bias da rede.

6. **`initialize_parameters(n_input=784, n_hidden=128, n_output=10)`**:
   - **Descrição**: Inicializa os pesos e bias da rede neural com valores aleatórios pequenos.
   - **Parâmetros**:
     - `n_input`: Número de neurônios na camada de entrada (784 para imagens MNIST).
     - `n_hidden`: Número de neurônios na camada oculta.
     - `n_output`: Número de neurônios na camada de saída (10 para dígitos de 0 a 9).

7. **`forward_propagation(x, W1, b1, W2, b2)`**:
   - **Descrição**: Executa uma passagem para frente, calculando as saídas da rede a partir das entradas.
   - **Parâmetros**:
     - `x`: Dados de entrada.
     - `W1, b1, W2, b2`: Pesos e bias da rede.

8. **`backward_propagation(x, y, W1, b1, W2, b2, a1, y_hat)`**:
   - **Descrição**: Executa o backpropagation para calcular os gradientes dos pesos e bias, baseando-se no erro entre as previsões e os rótulos verdadeiros.
   - **Parâmetros**:
     - `x`: Dados de entrada.
     - `y`: Rótulos verdadeiros.
     - `W1, b1, W2, b2, a1, y_hat`: Pesos, bias e ativações da rede.

9. **`train(x_train, y_train, W1, b1, W2, b2, eta=0.01, epochs=1000)`**:
   - **Descrição**: Treina a rede usando os dados de treinamento, ajustando os pesos e bias para minimizar a perda.
   - **Parâmetros**:
     - `x_train`: Dados de treinamento.
     - `y_train`: Rótulos de treinamento.
     - `W1, b1, W2, b2`: Pesos e bias da rede.
     - `eta`: Taxa de aprendizagem.
     - `epochs`: Número de épocas de treinamento.

10. **`load_mnist()`**:
    - **Descrição**: Carrega os dados do conjunto de dados MNIST, normalizando os valores de pixel e convertendo os rótulos em one-hot encoding.
    - **Saída**: Retorna os conjuntos de dados de treino e teste.

#### Diagrama da Rede Neural:

A seguir está o diagrama da rede neural:

```
[ 784 ] -- [ 128 ] -- ReLU -- [ 10 ] -- Softmax
```

- **[784]**: Camada de entrada, uma para cada pixel em imagens MNIST de 28x28.
- **[128]**: Camada oculta com 128 neurônios.
- **ReLU**: Função de ativação ReLU usada após a primeira camada oculta.
- **[10]**: Camada de saída com 10 neurônios, um para cada classe de dígito (0-9).
- **Softmax**: Função de ativação Softmax usada para normalizar as saídas em uma distribuição de probabilidade.

Este repositório oferece uma base sólida para entender e explorar redes neurais aplicadas ao problema clássico de reconhecimento de dígitos escritos à mão.
