# INSERTION-SORT
#include <stdio.h>

//ordena o vetor utilizando Insertion Sort
void insertionSort(int vet[], int tam) {
    int x, y, chave;

    for (x = 1; x < tam; x++) {
        //o laço 'x' percorre a partir do elemento na posição 1
		chave = vet[x];
        y = x - 1;
        
		//ele vai mover o elemento atual (y) para a posição correta no vetor 
        while (y >= 0 && vet[y] > chave) {
            //realiza a troca dos elementos
			vet[y + 1] = vet[y];
            y--;
        }

        vet[y + 1] = chave;
    }
}

//imprime o vetor
void imprimirVetor(int vet[], int tam) {
    int i;
    for (i = 0; i < tam; i++) {
        printf("%d ", vet[i]);
    }
    printf("\n");
}

int main() {
    int vet[] = {33, 22, 19, 76, 98, 67, 53}; //numeros escolhidos por mim mesmo
    int tam = sizeof(vet) / sizeof(vet[0]);

    printf("Vetor original: ");
    imprimirVetor(vet, tam);

    insertionSort(vet, tam);

    printf("Vetor ordenado: ");
    imprimirVetor(vet, tam);

    return 0;
}
