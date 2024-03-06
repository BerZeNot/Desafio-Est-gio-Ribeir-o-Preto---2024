# Desafio-Est-gio-Ribeir-o-Preto---2024
Repositório para salvar as respostas do desafio Estágio Ribeirão Preto - 2024

### 1) Observe o trecho de código abaixo:

int INDICE = 13, SOMA = 0, K = 0;

enquanto K < INDICE faça

{

K = K + 1;

SOMA = SOMA + K;

}

imprimir(SOMA);



Ao final do processamento, qual será o valor da variável SOMA?
#### Resposta: 12;
--- 
### 2) Dado a sequência de Fibonacci, onde se inicia por 0 e 1 e o próximo valor sempre será a soma dos 2 valores anteriores (exemplo: 0, 1, 1, 2, 3, 5, 8, 13, 21, 34...), escreva um programa na linguagem que desejar onde, informado um número, ele calcule a sequência de Fibonacci e retorne uma mensagem avisando se o número informado pertence ou não a sequência.
#### Resposta:
```
#include <stdio.h>
#include <stdlib.h>

int fib(int n){
	if(n==1)
		return 0;
	else if(n==2)
		return 1;
	
	int n1=0, n2=1, aux=0;
	for(int i=2; i<=n; i++){
		aux = n1+n2;
		n1 = n2;
		n2 = aux;
	}
	return n2;
}

short isContainedInFibonacci(int n){
	for(int i=1; i<=n+2; i++){
		if(fib(i) == n)
			return 1;
	}
	return 0;
}

void showHelp(){
	printf("Using example:\n");
	printf("./isOnFib 17\n");
	printf("17 isn't contained on Fibonacci's sequence\n");
}

int main(int argc, char **argv){
	if(argc != 2){
		showHelp();
	} else {
		int numberToCheck = atoi(argv[1]);
		if(isContainedInFibonacci(numberToCheck))
			printf("%d is contained on Fibonacci's sequence\n", numberToCheck);
		else
			printf("%d isn't contained on Fibonacci's sequence\n", numberToCheck);		
	}
	return 0;
}
// Este código não funcionará com entradas que resultarão em um número da sequência
// de fibonacci que excede o valor máximo suportado por uma variável do tipo int.
```
---
### 3) Descubra a lógica e complete o próximo elemento:

a) 1, 3, 5, 7, *[9]*

b) 2, 4, 8, 16, 32, 64, *[128]*

c) 0, 1, 4, 9, 16, 25, 36, *[49]*

d) 4, 16, 36, 64, *[125]*

e) 1, 1, 2, 3, 5, 8, *[13]*

f) 2,10, 12, 16, 17, 18, 19, *[29]*

---
### 4) Você está em uma sala com três interruptores, cada um conectado a uma lâmpada em uma sala diferente. Você não pode ver as lâmpadas da sala em que está, mas pode ligar e desligar os interruptores quantas vezes quiser. Seu objetivo é descobrir qual interruptor controla qual lâmpada.

### Como você faria para descobrir, usando apenas duas idas até uma das salas das lâmpadas, qual interruptor controla cada lâmpada?

#### Resposta: 
1. Primeiro eu ligo os interruptores 1 e 2 e deixo-os ligados por alguns minutos.
2. Em seguida, desligo o interruptor 2.
3. Me dirijo até a sala 1.
4. Se a sala 1 estiver com a luz acesa, o interruptor 1 é da sala 1;
5. Senão, se a sala 1 estiver com o a luz apagada, porém com a lâmpada quente, o interruptor 2 é da sala 1;
6. Senão, o interruptor 3 é da sala 1. 
7. Aguardo algum tempo para que as lâmpadas esfriem.
8. Ligo os dois interruptores restantes, que não foram relacionados nos passos anteriores e aguardo alguns momentos.
9. Desligo o segundo dos interruptores e me dirijo à sala 2.
10. Se a lâmpada da sala 2 estiver acesa, o interruptor que ficou ligado é da sala 2 e o que ficou desligado é da sala 3.
11. Senão, o interruptor desligado é da sala 2 e o ligado é da sala 3.  
---
### 5) Escreva um programa que inverta os caracteres de um string.

IMPORTANTE:

a) Essa string pode ser informada através de qualquer entrada de sua preferência ou pode ser previamente definida no código;

b) Evite usar funções prontas, como, por exemplo, reverse;

#### Resposta:
```
#include <stdio.h>
#include <string.h>

int main(int argc, char **argv){
	if(argc !=2){
		printf("Use only 1 argument: ./revert strToRevert\n");
		return -1;
	} else {
		int len = (int) strlen(argv[1]);
		for(int i=len-1; i>=0; i--){
			printf("%c", argv[1][i]);
		}
		printf("\n");
	}
	return 0;
}
```
