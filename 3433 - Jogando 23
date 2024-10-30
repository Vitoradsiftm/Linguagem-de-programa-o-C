#include <stdio.h>


int obter_valor(int carta) {
    if (carta>10){
        carta=10;
    }
    return (carta);
}

int main() {
    int N;
    scanf("%d", &N);

    int joao1, joao2, maria1, maria2;
    int carta_comum[8];
    int pontos_joao, pontos_maria;
    int contador_cartas[14] = {0};

    scanf("%d %d", &joao1, &joao2);
    scanf("%d %d", &maria1, &maria2);

    contador_cartas[joao1]++;
    contador_cartas[joao2]++;
    contador_cartas[maria1]++;
    contador_cartas[maria2]++;

    for (int i = 0; i < N; i++) {
        scanf("%d", &carta_comum[i]);
        contador_cartas[carta_comum[i]]++;
    }


    pontos_joao = obter_valor(joao1) + obter_valor(joao2);
    pontos_maria = obter_valor(maria1) + obter_valor(maria2);


    for (int i = 0; i < N; i++) {
        int valor_comum = obter_valor(carta_comum[i]);
        pontos_joao += valor_comum;
        pontos_maria += valor_comum;
    }


    int menor_carta = -1;
    for (int i = 1; i <= 13; i++) {
        if (contador_cartas[i] < 4) {
            int valor = obter_valor(i);
            int pontos_novos_maria = pontos_maria + valor;
            int pontos_novos_joao = pontos_joao + valor;

            if (pontos_novos_maria == 23 && pontos_novos_joao != 23) {
                menor_carta = i;
                break;
            } else if (pontos_novos_joao > 23 && pontos_novos_maria <= 23) {
                menor_carta = i;
                break;
            } else if(pontos_novos_maria == 23 && pontos_novos_joao == 23){
                menor_carta = i;
                break;
            }
        }
    }

    printf("%d\n", menor_carta);

    return 0;
}
