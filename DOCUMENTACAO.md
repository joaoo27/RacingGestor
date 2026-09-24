# Título do Projeto: RacingGestor — Sistema de Gerenciamento de Campeonato de Fórmula 1

## 1. Descrição do Sistema

O **RacingGestor** é um sistema desenvolvido em linguagem C para auxiliar no gerenciamento de campeonatos de Fórmula 1. O problema que ele busca resolver é a dificuldade de manter, de forma centralizada e organizada, as informações de pilotos, equipes, pistas, corridas e resultados. Quando esses dados são controlados manualmente ou ficam distribuídos, podem ocorrer duplicidades, perda de informações e dificuldades para localizar os resultados e acompanhar a pontuação do campeonato.

Para solucionar esse problema, o sistema permite cadastrar e consultar pilotos, equipes, pistas e corridas, mantendo o relacionamento entre esses registros. Também é possível registrar o resultado de cada corrida, associando-a à pista utilizada e armazenando a posição obtida por cada piloto. A partir dessas posições, os pontos correspondentes são calculados e atribuídos aos pilotos e às equipes, facilitando o acompanhamento da classificação.

Dessa forma, o **RacingGestor** oferece uma solução simples e estruturada para organizar os dados do campeonato, reduzir inconsistências nos cadastros e tornar mais ágil a consulta das informações e dos resultados das corridas.

## 2. Fluxo de Utilização Esperado para o Sistema

## 3. Fluxograma da Lógica do Sistema
![Fluxograma Principal](Fluxograma.jpg)

## 4. Estrutura de Dados

O **RacingGestor** utilizará as seguintes estruturas heterogêneas (structs) para organizar e armazenar os dados de pilotos, equipes, pistas, corridas e resultados do campeonato.

```c
// Estrutura para armazenamento dos Pilotos
typedef struct {
    int id_piloto;
    char nome[100];
    int numero;
    char nacionalidade[50];
    int id_equipe;
    int pontos;
} Piloto;

// Estrutura para armazenamento das Equipes
typedef struct {
    int id_equipe;
    char nome[100];
    char pais[50];
    int pontos;
} Equipe;

// Estrutura para armazenamento das Pistas
typedef struct {
    int id_pista;
    char nome[100];
    char pais[50];
    int numero_voltas;
} Pista;

// Estrutura para armazenamento das Corridas
typedef struct {
    int id_corrida;
    char nome[100];
    int id_pista;
    char data[11];
} Corrida;

// Estrutura para armazenamento dos Resultados
typedef struct {
    int id_resultado;
    int id_corrida;
    int id_piloto;
    int posicao;
    int pontos;
} Resultado;
```
