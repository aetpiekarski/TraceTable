# ARTEFATOS PARA TESTE DE MESA: MODELOS, EXEMPLOS E EXERCÍCIOS

Nas disciplinas introdutórias de Algoritmos e Programação de Computadores, a resolução dos exercícios propostos deve envolver as seguintes etapas:
 • Planejamento: projetar a solução, listando os dados de entrada, as etapas de processamento necessárias e os dados de saída, contemplando os componentes abstração, decomposição e reconhecimento de padrões do PC;
 • Solução algorítmica: desenvolver o fluxograma e/ou pseudocódigo, buscando generalizar a partir de casos reais ou exemplos disponíveis (componentes generalização e algoritmos do PC);
 • Testes: validar a solução, utilizando os artefatos disponibilizados (e, caso necessário, retomar as etapas anteriores para corrigir ou complementar a solução) (componente depuração do PC);
 • Implementação: codificar a solução em uma linguagem de alto nível (C/C++).
 
Os estudantes são encorajados a desenvolver esse conjunto de passos (exceto a implementação) de forma manuscrita. A metodologia de atividade desplugada contribui para a disseminação dos artefatos, pois não exige recursos computacionais e possibilita que sejam utilizados desde o ensino médio/técnico até o superior, ou em atividades de ensino destinadas à disseminação dos conceitos de PC, algoritmos e programação.
Para cada tópico abordado, são disponibilizados exemplos, que constituem um referencial facilitador para o aprendizado, incluindo todas essas etapas (Exemplo 1, ilustrado abaixo). O uso de fluxogramas é muito adequado, pois trata-se de uma representação de mais alto nível, intuitiva à leitura, que permite a visualização dos fluxos de execução principalmente quanto às estruturas de seleção e repetição.

![Exemplo incluindo todas as etapas para desenvolvi
mento de umasolução algoritmica](exemplo.png)

Para um teste de mesa, uma lista das variáveis e a atribuição dos valores aos longo do algoritmo é suficiente; é importante que o teste seja feito com mais de uma instância. Cada conjunto de dados (um exemplo concreto) de um teste define uma instância do problema. É importante avaliar especialmente o comportamento do algoritmo com os valores limites, conforme o contexto do problema.

Em um algoritmo, as variáveis constituem símbolos, assim como na notação matemática; no entanto, quando se considera que o algoritmo será traduzido para uma linguagem e executado por um computador, deve-se deixar claro que as variáveis representam posições de memória.

Uma representação adequada de um teste de mesa é por meio de uma tabela, organizada em quatro seções, conforme o título das colunas:
\begin{itemize}
    \item \#: o identificador de uma instância de teste;
    \item Entrada: as variáveis que são informadas pelo usuário quando da realização de uma instância de teste;
    \item Processamento: o conjunto das variáveis utilizadas no algoritmo (além das de entrada) e as  expressões lógicas (condições), quando há estruturas condicionais ou de repetição. As colunas das condições serão preenchidas com os valores lógicos, conforme as instâncias;
    
    \item Saída: as respostas do algoritmo, incluindo valores de variáveis e textos.  
\end{itemize}

     
O funcionamento do algoritmo deve ser simulado linha-a-linha. Cada instrução deve refletir sua ação, alterando os valores das variáveis e assinalando o resultados das condições no teste de mesa.

## Teste de mesa de algoritmos sequenciais

Para listar as variáveis nas colunas, é aconselhável que sigam a ordem de ocorrência no pseudocódigo, facilitando o preenchimento.

O primeiro exemplo apresentado (Algoritmo~\ref{alg:Soma}) pede a soma de dois valores numéricos, cuja solução consiste em uma instrução de entrada, uma expressão aritmética e uma instrução de saída. 

\begin{minipage}{0.95\linewidth}
\begin{lstlisting}[label={alg:Soma}, caption={Soma}]
Algoritmo "Soma"
// Descrição: Soma dois valores numéricos inteiros
Var
  x, y, soma : inteiro
Inicio
  leia (x, y)
  soma <- x + y
  escreva (soma)
Fimalgoritmo
\end{lstlisting}
\,
\end{minipage}

No teste de mesa (Figura \ref{fig:testeSoma}), a primeira coluna numera a instância de teste (coluna indicada por \#). Depois, são representadas as variáveis {\fontfamily{pcr}\selectfont x} e {\fontfamily{pcr}\selectfont y}, explicitadas como valores de entrada, a variável {\fontfamily{pcr}\selectfont soma}, como variáveis envolvida no processamento, e a coluna Saída, em que são mostrados os valores da instrução de saída. Para cada instância (neste teste constam 4 instâncias), são atribuídos os valores para as variáveis de entrada a critério do estudante (instrução leia da linha 6), realizado o cálculo, atribuindo o resultado à variável {\fontfamily{pcr}\selectfont soma} (cálculo da linha 7) e mostrado o valor da variável {\fontfamily{pcr}\selectfont soma} na coluna Saída (conforme a instrução escreva da linha 8). 

\begin{figure}[ht]
\centering\includegraphics[width=0.8\linewidth]{figures/testeSoma.png}\par  
  \caption{Teste de mesa para o algoritmo Soma.}
  \Description{Teste de mesa para o algoritmo Soma.}
  
\end{figure}

Quando há a sobreposição de valor em uma variável, isso deve ficar explícito no teste, sendo possível visualizar toda a evolução dos valores. Assim, os valores devem ser cortados com um traço (usa-se o efeito tachado nos exemplos editados digitalmente) e o novo valor é indicado ao lado. Essa situação pode ser vista no exemplo do Algoritmo~\ref{alg:Troca}, que demostra a troca de valores entre duas variáveis.

\begin{minipage}{0.95\linewidth}
\begin{lstlisting}[label={alg:Troca}, caption={Troca}]
Algoritmo "Troca"
// Descrição: Troca de conteúdo de duas variáveis
Var
   a, b, aux : inteiro
Inicio
   leia (a, b)
   aux <- a
   a <- b
   b <- aux
   escreva (a, b)
Fimalgoritmo
\end{lstlisting}
\,
\end{minipage}

No teste de mesa (Figura \ref{fig:testeTroca}), o conteúdo das variáveis {\fontfamily{pcr}\selectfont a} e {\fontfamily{pcr}\selectfont b} é substituído quando as instruções das linhas 9 e 10 são executadas.

\begin{figure}[ht]
  
  \centering\includegraphics[width=0.8\linewidth]{figures/testeTroca.png}\par  
  \caption{Teste de mesa para o algoritmo Troca }
  \Description{Teste de mesa para o algoritmo Troca}
  
\end{figure}

Outra situação que deve ser observada é com relação à inicialização de variáveis. Embora, no papel, as variáveis representadas estejam inicialmente vazias, após codificado o algoritmo (dependendo da linguagem utilizada), se as variáveis não tiverem sido inicializadas, um valor não conhecido poderá ser recuperado (lixo de memória) e resultar em erros de execução. Essa situação é ilustrada com um exercício, em que é pedida a descrição da funcionalidade do Algoritmo~\ref{alg:Inicializa}.

\begin{minipage}{0.95\linewidth}
\begin{lstlisting}[label={alg:Inicializa}, caption={Inicialização de variável}]
Algoritmo "Troca"
// Descrição: Avalia inicializacao
   a, b, aux : inteiro
Inicio
   leia (a)
   a <- b
   leia (b)
   aux <- a
   b <- aux
   escreva (a, b)
Fimalgoritmo
\end{lstlisting}
\,
\end{minipage}

Ao se depararem com a instrução da linha 6, os aprendizes percebem que a variável {\fontfamily{pcr}\selectfont b} não tem valor e questionam o que acontece com o algoritmo e como devem proceder. Nesse caso, são estimulados a descrever que a variável não tinha valor atribuído e, portanto, não é possível saber quais valores serão mostrados.

## Teste de mesa de estruturas de seleção
Para fazer o teste de mesa de uma estrutura de seleção, cada condição deve constituir uma coluna da tabela, indicada entre parênteses e com um sinal de interrogação (conforme a Figura \ref{fig:testeSelecao}). 
Por exemplo, {\fontfamily{pcr}\selectfont (a>b)? (n\
Nos casos de teste, essas colunas recebem os valores da avaliação da condição para cada vez que a linha da condição for alcançada (V ou F). 

\begin{figure}[ht]
  
  \centering\includegraphics[width=1\linewidth]{figures/testeSelecao.png}\par 
  \caption{Exemplo de teste de mesa para estrutura de seleção}
  \Description{Exemplo de teste de mesa para estrutura de seleção}
  
\end{figure}

Em estruturas de seleção aninhadas, as condições que não são avaliadas devem ser assinaladas com um hífen, deixando claro que o fluxo de execução do algoritmo foi desviado antes dessa condição. Um exemplo simples é o Algoritmo~\ref{alg:Maior}, com apenas uma estrutura aninhada. No teste de mesa (Figura \ref{fig:testeMaior}), é possível ver na primeira instância a condição {\fontfamily{pcr}\selectfont (a < b)?} assinalada com hífen.

\begin{minipage}{0.95\linewidth}
\begin{lstlisting}[label={alg:Maior}, caption={Maior}]
Algoritmo "Maior de dois"
// Descrição: Maior valor com estrutura de seleção aninhada
Var
   a, b : inteiro
Inicio
   leia (a, b)
   se (a > b) entao
      escreva ("A é maior")
   senao
      se (a < b) entao
         escreva ("B é maior")
      senao
         escreva ("A e B sao iguais")
      fimse
   fimse
Fimalgoritmo
\end{lstlisting}
\,
\end{minipage}

\begin{figure}[ht]
  
  \centering\includegraphics[width=0.9\linewidth]{figures/testeMaior.png}\par 
  \caption{Teste de mesa para o algoritmo Maior}
  \Description{Teste de mesa para o algoritmo Maior}
  
\end{figure}

Para alguns problemas, é adequado um teste de mesa exaustivo, que consiste em explorar todos os fluxos de execução possíveis de um algoritmo. Como exemplo, considere o problema da ordenação de três valores numéricos. Para três valores, quais as combinações possíveis? Quais trocas são necessárias para ordenar cada um desses conjuntos? Uma solução é o Algoritmo~\ref{alg:Ordena}. 
 
\begin{minipage}{0.95\linewidth}
\begin{lstlisting}[label={alg:Ordena}, caption={Ordena}]
Algoritmo "Ordena"
// Descrição: Ordenacao de três valores usando estruturas de 
//            selecao alinhadas
Var
   a, b, c, aux : inteiro
Inicio
   leia (a, b, c)
   se (a > b) entao
      aux <- a
      a <- b
      b <- aux
   fimse
   se (b > c) entao
      aux <- b
      b <- c
      c <- aux
   fimse
   se (a > b) entao
      aux <- a
      a <- b
      b <- aux
   fimse
   escreva (a, b, c)
Fimalgoritmo
\end{lstlisting}
\,
\end{minipage}

No teste da Figura \ref{fig:testeOrdena}, é possível verificar, nas colunas das condições, que todas as combinações possíveis foram testadas, garantindo a corretude do algoritmo.

\begin{figure}[ht]
  
  \centering\includegraphics[width=1\linewidth]{figures/testeOrdena.png}\par  
  \caption{Teste de mesa para o algoritmo Ordena}
  \Description{Teste de mesa para o algoritmo Ordena}
  
\end{figure}

Para os algoritmos com estrutura de seleção múltipla (escolha-caso), cada caso deve ser considerado em uma coluna, explicitando a condição. O teste do Algoritmo~\ref{alg:Calculadora}, mostrado na Figura \ref{fig:testeCalculadora}, apresenta uma instância para cada caso da estrutura. Quando uma das condições é satisfeita, as demais não são avaliadas (indicado na coluna com um hífen). Na última instância, está representada a entrada não prevista em nenhum dos casos, em que é executada a cláusula {\fontfamily{pcr}\selectfont outrocaso} (linha 17).  

\begin{minipage}{0.95\linewidth}
\begin{lstlisting}[label={alg:Calculadora}, caption={Calculadora}]
Algoritmo "Calculadora"
// Descrição: Calculadora simples com estrutura de selecao multipla
var
   op : caractere
   a, b, r : real
inicio
   leia (op, a, b)
   escolha (op)
      caso "+"
           r <- a + b
      caso "-"
           r <- a - b
      caso "*"
           r <- a * b
      caso "/"
           r <- a / b
      outrocaso
           r <- 0
   fimescolha
   escreva (a, op, b, " = ", r)
fimalgoritmo
\end{lstlisting}
\,
\end{minipage}

\begin{figure}[ht]
  \centering\includegraphics[width=1\linewidth]{figures/testeCalculadora.png}\par  
  \caption{Teste de mesa para o algoritmo Calculadora}
  \Description{Teste de mesa para o algoritmo Calculadora}
  
\end{figure}

## Teste de mesa de estruturas de repetição
Para fazer o teste de mesa de algoritmos com estruturas de repetição, cada iteração será representada por uma linha. Nesses casos, cada instância ocupará várias linhas. Para ilustrar essa estrutura, considere o Algoritmo~\ref{alg:MaiordeN}, que tem como objetivo encontrar o maior dentre N valores lidos. 

\begin{minipage}{0.95\linewidth}
\begin{lstlisting}[label={alg:MaiordeN}, caption={Maior de N}]
Algoritmo "Maior de N"
// Descrição: Identifica o maior dentre n valores lidos
Var
   n, x, maior, i : inteiro
Inicio
   maior <- 0
   leia (n)
   para i de 1 ate n passo 1 faca
      leia (x)
      se (x > maior) entao
         maior <- x
      fimse
   fimpara   
   escreva (maior)
Fimalgoritmo
\end{lstlisting}
\,
\end{minipage}

Se o valor de uma variável é alterado, o novo valor deve constar na linha da iteração em que ocorre a atribuição.
A Figura \ref{fig:testeMaiordeN} apresenta duas instâncias de teste para o Algoritmo \ref{alg:MaiordeN}. Quando a condição de parada é atingida, a condição da linha 10, que é interna ao bloco da estrutura de repetição, não é avaliada e, portanto, assinalada com um hífen.

\begin{figure}[ht]
  \centering\includegraphics[width=1\linewidth]{figures/testeMaiordeN.png}\par  
  \caption{Teste de mesa para o algoritmo Maior de N}
  \Description{Teste de mesa para o algoritmo Maior de N}
  
\end{figure}

Como exemplo de estrutura de repetição pós-teste, considere o Algoritmo \ref{alg:ChicoJuca}, uma solução para o problema: 
``Chico tem 1,50m e cresce 2 cm por ano, enquanto Juca tem 1,10m e cresce 3 cm por ano. 
Quantos anos serão necessários para que Juca seja maior que Chico?''

\begin{minipage}{0.95\linewidth}
\begin{lstlisting}[label={alg:ChicoJuca}, caption={Chico e Juca}]
Algoritmo "Chico e Juca"
// Descrição: Calcula quantos anos são necessários para que 
//            Juca seja maior do que Chico
Var
   anos : inteiro
   Chico, Juca : real
Inicio
   Chico <- 1.50
   Juca < - 1.10
   anos <- 0
   repita 
      Chico <- Chico + 0.02
      Juca <- Juca + 0.03
      anos <- anos + 1
   ate Juca > Chico
   escreva (anos)
Fimalgoritmo
\end{lstlisting}
\,
\end{minipage}

Na Figura \ref{fig:testeChicoJuca}, o longo teste de mesa foi suprimido (como indicado pelas reticências), apresentando as primeiras e as últimas iterações. Outra peculiaridade deste algoritmo é que não há dado de entrada, portanto, apenas uma instância de teste.

\begin{figure}[ht]
  \centering\includegraphics[width=1\linewidth]{figures/testeDobro.png}\par  
  \caption{Teste de mesa para o algoritmo Chico e Juca}
  \Description{Teste de mesa para o algoritmo Chico e Juca}
  
\end{figure}

## Teste de mesa com vetores

Nos testes de mesa, os vetores devem ser representados posição a posição, seguindo a definição da estrutura (posições contíguas de memória com acesso direto a partir do índice). Como exemplo, considere o Algoritmo \ref{alg:Dobro}, que, a partir de um valor lido, calcula o dobro e armazena, preenchendo um vetor de tamanho 10 (cada posição tem o dobro da posição anterior). 

\begin{minipage}{0.95\linewidth}
\begin{lstlisting}[label={alg:Dobro}, caption={Dobro}]
Algoritmo "Dobro"
// Descrição: A partir de um valor lido, calcula o dobro 
//            do valor e guarda em um vetor 
Var
   num, i : inteiro
   N : vetor [1 .. 10] de inteiro
Inicio
   leia (num)
   para i de 1 até 10 faca
        N[i] <- num
        num <- num * 2
        escreva ("N[", i, "]=", N[i])
   fimpara
Fimalgoritmo
\end{lstlisting}
\,
\end{minipage}

No teste de mesa (Figura \ref{fig:testeDobro}), pode-se observar a atribuição em cada posição do vetor conforme as iterações do bloco de repetição.   

\begin{figure}[ht]
\centering\includegraphics[width=1\linewidth]{figures/testeDobro.png}\par  
  \caption{Teste de mesa para o algoritmo Dobro}
  \Description{Teste de mesa para o algoritmo Dobro}
  
\end{figure}

O Algoritmo \ref{alg:Horas} tem como funcionalidade armazenar as horas trabalhadas por dia do mês, em um vetor, e totalizar as horas do mês. Para isso, usa uma estrutura de repetição pré-teste para a inserção dos valores no vetor e uma estrutura contada (para-faça) para a totalização. Além disso, uma das informações de entrada é usada como índice do vetor, o que contribui para a compreensão do acesso a uma posição específica do vetor.

\begin{minipage}{0.95\linewidth}
\begin{lstlisting}[label={alg:Horas}, caption={Horas trabalhadas}]
Algoritmo "Horas trabalhadas"
// Descrição: Armazena as horas trabalhadas por dia e  
//            totaliza as horas do mês
Var
   dia, horas, i : inteiro
   ht : vetor [1 .. 31] de inteiro
Inicio
   leia (dia)
   enquanto (dia <> 0) faca
        leia (horas)
        ht[dia] <- horas
        leia (dia)
   fimenquanto
   horas <- 0
   para i de 1 até 31 faca
        horas <- horas + ht[i]
   fimpara
   escreva (horas, " horas")
Fimalgoritmo
\end{lstlisting}
\,
\end{minipage}

No teste de mesa (Figura \ref{fig:testeHoras}), é possível identificar as duas estruturas de repetição distintas (uma para a entrada dos dados, outra para a totalização das horas). 

\begin{figure}[ht]
\centering\includegraphics[width=1\linewidth]{figures/testeHoras.png}\par  
  \caption{Teste de mesa para o algoritmo Horas trabalhadas}
  \Description{Teste de mesa para o algoritmo Horas trabalhadas}
  
\end{figure}

## Observações gerais
Em códigos mais extensos, o teste de mesa é restrito ao bloco de processamento destinado à resolução do problema.

Quando há inicialização de variáveis, em algoritmos com estruturas de repetição, sugere-se que a primeira linha do teste seja destinada aos valores iniciais, antes que uma instância de teste comece. 

Essas situações ocorrem em testes de algoritmos com vetor. Como o preenchimento do vetor pode ser considerado trivial, o teste deve se dedicar ao fragmento do algoritmo (ou função) que contém a lógica central do problema. A primeira linha do teste contém os valores armazenados no vetor, sobre os quais será verificada a funcionalidade.
