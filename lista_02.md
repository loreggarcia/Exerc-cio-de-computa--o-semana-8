# Instruções

- Faça uma cópia deste arquivo .md para um repositório próprio
- Resolva as 6 questões objetivas assinalando a alternativa correta
- Resolva as 4 questões dissertativas escrevendo no próprio arquivo .md
  - lembre-se de utilizar as estruturas de código como ``esta aqui com ` `` ou
```javascript
//esta aqui com ```
let a = "olá"
let b = 10
print(a)
```
- Resolva as questões com uso do Visual Studio Code ou ambiente similar.
- Teste seus códigos antes de trazer a resposta para cá.
- Cuidado com ChatGPT e afins: entregar algo só para ganhar nota não faz você aprender e ficar mais inteligente. Não seja dependente da máquina! (E não se envolva em plágio!)
- ao final, publique seu arquivo lista_02.md com as respostas em seu repositório, e envie o link pela Adalove. 

# Questões objetivas

**1)** Considere o seguinte código JavaScript:

```javascript
//EX01
let p = 10;
let q = 3;
let r = 6;

let resultado = (p % q === 1) && (r * 2 > p) || (q + r < p);
console.log(resultado);

const valores = [3, 6, 9, 12, 15];
let produto = 1;

for (let j = 0; j < valores.length; j++) {
  produto *= valores[j];
}

console.log("O produto dos valores é:", produto);


```
Qual das seguintes alternativas melhor descreve o que o código faz?

A) O código avalia a expressão booleana, imprime `true`, calcula o produto dos números na lista e imprime o resultado no console.

B) O código avalia a expressão booleana, imprime `false`, calcula o produto dos números na lista e imprime o resultado no console.

C) O código avalia a expressão booleana, imprime `true` e, em seguida, verifica se o número 6 está na lista.

D) O código avalia a expressão booleana, imprime `false` e ordena os valores em ordem crescente.

Resposta: A resposta correta é a letra A. Na primeira parte, três variáveis são definidas: p = 10, q = 3 e r = 6. A expressão lógica verificada é:(p % q === 1) && (r * 2 > p) || (q + r < p). Ao analisar cada trecho separadamente, temos que p % q === 1 resulta em true, pois 10 % 3 deixa um resto de 1. Já r * 2 > p também é verdadeiro, pois 6 * 2 resulta em 12, que é maior que 10. Como ambas as condições anteriores estão conectadas por um operador lógico "E" (&&), o resultado dessa parte é true. Além disso, a última verificação q + r < p também é true, pois 3 + 6 resulta em 9, que de fato é menor que 10. Como essa parte da expressão está conectada ao restante por um operador lógico "OU" (||), basta que qualquer um dos lados seja verdadeiro para que o resultado final seja true. Assim, console.log(resultado); imprimirá true no console. Na segunda parte do código, um array contendo os números [3, 6, 9, 12, 15] é definido. Um laço de repetição percorre esse array e multiplica cada um de seus elementos, acumulando o resultado na variável produto, e esse resultado é imprimido no console. Portanto, o primeiro código avalia uma expressão lógica, imprime true, e após isso, calcula e imprime o produto dos números do array. 
______

**2)** O código a seguir contém duas funções que calculam o limite de crédito de um cliente com base nos seus gastos e na renda mensal.

```javascript
// Versão 1 da função de análise de crédito
function analisarCredito1() {
    var compras = [2500, 1200, 800, 100];
    var totalCompras = compras[0];
    var limite = 5000;
    var status = 'aprovado';
    var saldoDisponivel = 0;
    var i = 1;

    do {
        totalCompras += compras[i];
        i++;
    } while (limite >= totalCompras && i < compras.length);

    saldoDisponivel = limite - totalCompras;

    if (saldoDisponivel < 0) {
        status = 'negado';
    }
    console.log(`Seu crédito foi ${status}. Saldo disponível: ${saldoDisponivel}.`);
}
```

```javascript
// Versão 2 da função de análise de crédito
function analisarCredito2() {
    var compras = [2500, 1200, 800, 100];
    var totalCompras = compras[0];
    var limite = 5000;
    var status = 'aprovado';
    var saldoDisponivel = 0;
    var i = 1;

    while (limite >= totalCompras && i < compras.length) {
        totalCompras += compras[i];
        i++;
    }

    saldoDisponivel = limite - totalCompras;

    if (saldoDisponivel < 0) {
        status = 'negado';
    }
    console.log(`Seu crédito foi ${status}. Saldo disponível: ${saldoDisponivel}.`);
}
```
Se ambas as funções forem executadas com os valores fornecidos, qual será a saída exibida no console?

A) Ambas as funções exibirão: 'Seu crédito foi aprovado. Saldo disponível: 400.'

B) analisarCredito1() exibirá: 'Seu crédito foi negado. Saldo disponível: -600.', enquanto analisarCredito2() exibirá: 'Seu crédito foi negado. Saldo disponível: -200.'

C) analisarCredito1() exibirá: 'Seu crédito foi negado. Saldo disponível: -200.', enquanto analisarCredito2() exibirá: 'Seu crédito foi aprovado. Saldo disponível: 100.'

D) Ambas as funções exibirão: 'Seu crédito foi aprovado Saldo disponível: 500.'

Resposta: A resposta será a letra A. Isso ocorre porque a estrutura do...while da primeira função permite que a primeira compra seja somada mesmo que ultrapasse o limite, enquanto a estrutura while da segunda função impede que a soma ocorra quando o limite já está prestes a ser excedido. Isso acontece, porque, while verifica a condição antes de executar o bloco de código. Se a condição for falsa desde o início, o bloco nunca será executado.
do...while executa o bloco pelo menos uma vez, pois a condição só é verificada depois da primeira execução.

**3)** Considere o seguinte trecho de código em JavaScript:
```javascript
//EX03
const idade = 21;

if (idade >= 18 && idade < 60) {
  console.log("Você é um adulto!");
} else if (idade < 18) {
  console.log("Você é menor de idade!");
} else {
  console.log("Você está na melhor idade!");
}
```
Qual das seguintes alternativas melhor descreve o comportamento do código?

A) O código verifica se a idade indica um adulto ou um idoso e exibe a mensagem correspondente.

B) O código verifica se a idade pertence à faixa adulta. Se for, exibe "Você é um adulto!". Caso contrário, verifica se é menor de idade e exibe "Você é menor de idade!". Se nenhuma das condições anteriores for verdadeira, exibe "Você está na melhor idade!".

C) O código verifica se a idade está entre 18 e 60 anos e, se for, imprime "Você é um adulto!". Se não estiver nesse intervalo, imprime "Você está na melhor idade!".

D) O código verifica se a idade é menor de 18, entre 18 e 60 ou acima de 60, imprimindo uma mensagem específica para cada caso.

Resposta: A resposta é letra B, pois o código utiliza uma estrutura condicional para classificar a idade. Primeiro, verifica se a idade está entre 18 e 59 anos (idade >= 18 && idade < 60). Se essa condição for verdadeira, o código executa essa condição e encerra a verificação. Caso não, verifica se a idade é menor que 18 (idade < 18). Se for, executa esse bloco. Se nenhuma das condições anteriores for atendida, vai para else, e executa essa condição.
______

**4)** Qual será o resultado impresso no console após a execução do seguinte código?
```javascript
//EX04
var energiaDisponivel = 1200;
var bateriaExtra = 400;
var consumoDispositivos = [300, 600, 500, 200, 400];

for (var i = 0; i < consumoDispositivos.length; i++) {
    var consumo = consumoDispositivos[i];

    if (consumo <= energiaDisponivel) {
        console.log("Dispositivo " + (i+1) + " ligado. Energia restante: " + (energiaDisponivel - consumo));
        energiaDisponivel -= consumo;
    } else if (consumo <= energiaDisponivel + bateriaExtra) {
        console.log("Dispositivo " + (i+1) + " ligado com bateria extra. Energia restante: " + ((energiaDisponivel + bateriaExtra) - consumo));
        energiaDisponivel = 0;
        bateriaExtra -= (consumo - energiaDisponivel);
    } else {
        console.log("Dispositivo " + (i+1) + " não pode ser ligado. Energia insuficiente.");
    }
}
```


Escolha a opção que responde corretamente:

A)
Dispositivo 1 ligado. Energia restante: 900

Dispositivo 2 ligado com bateria extra. Energia restante: 700

Dispositivo 3 ligado. Energia restante: 200

Dispositivo 4 ligado com bateria extra. Energia restante: 0

Dispositivo 5 ligado. Energia restante: -200

B)
Dispositivo 1 ligado. Energia restante: 900

Dispositivo 2 ligado com bateria extra. Energia restante: 700

Dispositivo 3 ligado. Energia restante: 200

Dispositivo 4 não pode ser ligado. Energia insuficiente.

Dispositivo 5 não pode ser ligado. Energia insuficiente.

C)
Dispositivo 1 ligado. Energia restante: 900

Dispositivo 2 ligado com bateria extra. Energia restante: 700

Dispositivo 3 ligado. Energia restante: 400

Dispositivo 4 não pode ser ligado. Energia insuficiente.

D)
Dispositivo 1 ligado. Energia restante: 900

Dispositivo 2 ligado. Energia restante: 300

Dispositivo 3 ligado com bateria extra. Energia restante: 200

Dispositivo 4 não pode ser ligado. Energia insuficiente.

Dispositivo 5 não pode ser ligado. Energia insuficiente.

Resposta: A resposta correta é a letra B. Pois, é a única resposta que condiz com a lógica do código.
______

**5)** Qual é a principal função do método update() em um jogo desenvolvido com Phaser.js?

Escolha a opção que melhor descreve seu propósito:

A) O método update() é responsável por carregar os assets do jogo antes da cena ser exibida.

B) O método update() é chamado continuamente a cada quadro (frame) do jogo, sendo usado para atualizar a lógica, movimentação e interações dos objetos na cena.

C) O método update() renderiza todos os sprites na tela e garante que a física do jogo seja processada corretamente.

D) O método update() é chamado apenas uma vez após a criação da cena, sendo utilizado para configurar variáveis iniciais do jogo.

Resposta: A resposta correta é letra B, pois é a única que condiz com o uso do update no phaser.
______

**6)** Qual é o principal objetivo do módulo Matter.js Physics em Phaser.js?

Escolha a opção que responde corretamente:

A) Simular física avançada, incluindo corpos rígidos, colisões complexas e interação entre objetos com gravidade e forças.

B) Gerenciar eventos de entrada do usuário, como cliques e toques na tela, permitindo movimentação de personagens.

C) Renderizar gráficos otimizados para jogos 2D e garantir uma taxa de quadros estável.

D) Criar animações automáticas para sprites e objetos interativos sem necessidade de programação de movimentação.

Resposta: A resposta é letra A, pois Matter.js é uma biblioteca de física 2D que integra o motor de física ao Phaser.js, permitindo simular comportamentos físicos realistas, como colisões, gravidade, forças, e interações entre objetos rígidos.
______

# Questões dissertativas

**7)** Uma loja online deseja implementar um sistema de classificação de pedidos com base no valor total da compra. O sistema deve determinar a categoria de um pedido com as seguintes regras:

```

Pedidos abaixo de R$50,00 → "Frete não disponível!"

Pedidos entre R$50,00 e R$199,99 (inclusive) → "Frete com custo adicional!"

Pedidos de R$200,00 ou mais → "Frete grátis!"

```
Implemente um pseudocódigo que receba o valor total da compra e exiba a classificação correta do frete para o cliente.

Resposta: 

Início
    // Solicita o valor total da compra ao usuário
    Escreva "Digite o valor total da compra: "
    Leia valorCompra

    // Verifica a faixa de preço e classifica o frete
    Se valorCompra < 50 então
        Escreva "Frete não disponível!"
    Senão Se valorCompra >= 50 e valorCompra <= 199.99 então
        Escreva "Frete com custo adicional!"
    Senão
        Escreva "Frete grátis!"
    Fim Se
Fim
______

**8)** Considere a implementação da classe base Veiculo em um sistema de modelagem de veículos. Sua tarefa é implementar, utilizando pseudocódigo, as classes derivadas Carro e Moto, que herdam da classe Veiculo, adicionando atributos específicos e métodos para calcular o consumo de combustível de um carro e de uma moto, respectivamente.

```
Classe Veiculo:
Atributos:

modelo
ano
Método Construtor(modelo, ano):

Define os valores dos atributos modelo e ano com os valores passados como parâmetro.
Método CalcularConsumo():
```
Implementação genérica para cálculo de consumo, a ser sobrescrita pelas subclasses.
Agora, implemente as classes Carro e Moto, garantindo que ambas herdem de Veiculo e possuam métodos específicos para calcular o consumo de combustível com base na quilometragem e eficiência do veículo.

// Classe base Veiculo
Classe Veiculo:
    Atributos:
        modelo
        ano

    Método Construtor(modelo, ano):
        this.modelo = modelo
        this.ano = ano

    Método CalcularConsumo():
        Escreva "Método CalcularConsumo deve ser sobrescrito pelas subclasses!"

// Classe derivada Carro, que herda de Veiculo
Classe Carro herda de Veiculo:
    Atributos:
        quilometragem
        eficiencia

    Método Construtor(modelo, ano, quilometragem, eficiencia):
        Chama o construtor da classe Veiculo(modelo, ano)
        this.quilometragem = quilometragem
        this.eficiencia = eficiencia

    Método CalcularConsumo():
        consumo = this.quilometragem / this.eficiencia
        Retorne consumo

// Classe derivada Moto, que herda de Veiculo
Classe Moto herda de Veiculo:
    Atributos:
        quilometragem
        eficiencia

    Método Construtor(modelo, ano, quilometragem, eficiencia):
        Chama o construtor da classe Veiculo(modelo, ano)
        this.quilometragem = quilometragem
        this.eficiencia = eficiencia

    Método CalcularConsumo():
        consumo = this.quilometragem / this.eficiencia
        Retorne consumo

// Exemplo de uso das classes
Início
    // Criando um carro
    carro = Novo Carro("Fusca", 1985, 600, 10)  // 600 km com 10 km/litro de eficiência
    Escreva "Consumo do carro: ", carro.CalcularConsumo()

    // Criando uma moto
    moto = Nova Moto("Honda CG", 2020, 450, 25)  // 450 km com 25 km/litro de eficiência
    Escreva "Consumo da moto: ", moto.CalcularConsumo()
Fim

______

**9)** Você é um cientista da NASA e está ajudando no desenvolvimento de um sistema de pouso para sondas espaciais em Marte. Seu objetivo é calcular o tempo necessário para que a sonda reduza sua velocidade até um nível seguro para pouso, considerando uma velocidade inicial de entrada na atmosfera marciana e uma taxa de desaceleração constante causada pelo atrito atmosférico e retrofoguetes.

Entretanto, a sonda não pode ultrapassar um tempo máximo de descida para evitar desvios orbitais, nem pode desacelerar além de um limite mínimo, pois isso poderia causar instabilidade no pouso.

Implemente a lógica dessa simulação em pseudocódigo, considerando a seguinte equação para atualização da velocidade:

Considere a fórumla de atualização velocidade:
```
    velocidade = velocidadeInicial - desaceleracao * tempo
Seu programa deve determinar quanto tempo será necessário para que a sonda atinja uma velocidade segura de pouso, sem ultrapassar os limites estabelecidos.

// Definir parâmetros de entrada
velocidadeInicial = 1500 // Velocidade inicial de entrada na atmosfera (em km/h)
velocidadeSegura = 10 // Velocidade segura para o pouso (em km/h)
desaceleracao = 50 // Taxa de desaceleração causada pelo atrito atmosférico e retrofoguetes (em km/h²)
tempoMaximo = 30 // Tempo máximo de descida (em horas)
desaceleracaoMinima = 5 // Desaceleração mínima para evitar instabilidade (em km/h²)

// Inicializar variáveis
tempo = 0
velocidadeAtual = velocidadeInicial

// Loop para simular a redução da velocidade
Enquanto velocidadeAtual > velocidadeSegura E tempo < tempoMaximo:
    // Atualiza a velocidade da sonda a cada unidade de tempo
    velocidadeAtual = velocidadeInicial - desaceleracao * tempo
    
    // Verificar se a desaceleração foi além do limite mínimo
    Se desaceleracao < desaceleracaoMinima:
        Escreva "Desaceleração mínima atingida. Ajuste necessário."
        Pare

    // Incrementa o tempo de descida
    tempo = tempo + 1 // Incrementa o tempo em uma unidade (ex: horas)

    // Se ultrapassou o tempo máximo, interrompe a simulação
    Se tempo >= tempoMaximo:
        Escreva "Tempo máximo de descida alcançado. Pouso instável possível!"
        Pare

// Verifica se a velocidade segura foi atingida dentro dos limites
Se velocidadeAtual <= velocidadeSegura:
    Escreva "Sonda atingiu a velocidade segura para o pouso em ", tempo, " horas."

Fim

```
______

**10)** Em um sistema de análise financeira, as operações de investimento de uma empresa podem ser representadas por matrizes, onde cada linha representa um tipo de investimento e cada coluna representa um período de tempo.

A seguir, é fornecida a implementação da função SomarMatrizesInvestimento(matrizA, matrizB), que soma os valores de duas matrizes de investimento. Sua tarefa é implementar uma função semelhante, porém que realize a multiplicação das matrizes de investimento, determinando como os investimentos afetam os resultados ao longo do tempo.



```
Função SomarMatrizesInvestimento(matrizA, matrizB):  
    # Verifica se as matrizes têm o mesmo número de linhas e colunas  
    Se tamanho(matrizA) ≠ tamanho(matrizB) então:  
        Retornar "As matrizes não podem ser somadas. Elas têm dimensões diferentes."  
    Senão:  
        linhas <- tamanho(matrizA)  
        colunas <- tamanho(matrizA[0])  
        matrizResultado <- novaMatriz(linhas, colunas)  

        # Loop para percorrer cada elemento das matrizes e calcular a soma  
        Para i de 0 até linhas-1 faça:  
            Para j de 0 até colunas-1 faça:  
                matrizResultado[i][j] <- matrizA[i][j] + matrizB[i][j]  

        Retornar matrizResultado  

# Exemplo de uso da função  
investimentosAno1 <- [[1000, 2000], [1500, 2500]]  
investimentosAno2 <- [[1200, 1800], [1300, 2700]]  

totalInvestimentos <- SomarMatrizesInvestimento(investimentosAno1, investimentosAno2)  
Escrever("Total de investimentos acumulados:")  
ImprimirMatriz(totalInvestimentos)  

Agora, implemente a função MultiplicarMatrizesInvestimento(matrizA, matrizB), que multiplica as duas matrizes, simulando o efeito de diferentes fatores de crescimento e impacto financeiro nos investimentos ao longo do tempo.

inicio
    funcao MultiplicarMatrizesInvestimento(matrizA, matrizB):  
        # Verifica se as matrizes podem ser multiplicadas (colunas de A == linhas de B)  
        se tamanho(matrizA[0]) ≠ tamanho(matrizB) entao:  
            retorna "As matrizes não podem ser multiplicadas. O número de colunas de A deve ser igual ao número de linhas de B."  
        senao:  
            linhasA <- tamanho(matrizA)  
            colunasA <- tamanho(matrizA[0])  
            colunasB <- tamanho(matrizB[0])  
            matrizResultado <- novaMatriz(linhasA, colunasB)  

            # Loop para multiplicar as matrizes  
            para i de 0 até linhasA - 1 faca:  
                para j de 0 até colunasB - 1 faca:  
                    matrizResultado[i][j] <- 0  
                    para k de 0 até colunasA - 1 faca:  
                        matrizResultado[i][j] <- matrizResultado[i][j] + (matrizA[i][k] * matrizB[k][j])  

            retorna matrizResultado  

    # Exemplo de uso da função  
    investimentosAno1 <- [[1000, 2000], [1500, 2500]]  
    fatoresCrescimento <- [[1.1, 0.9], [0.8, 1.2]]  

    impactoFinanceiro <- MultiplicarMatrizesInvestimento(investimentosAno1, fatoresCrescimento)  
    Escrever("Impacto financeiro dos investimentos:")  
    ImprimirMatriz(impactoFinanceiro)  
fim
