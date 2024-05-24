# Desenvolvimento-de-uma-Calculadora-em-Linguagem-C

Desenvolver uma calculadora em linguagem C é um excelente projeto para aplicar conceitos de programação e entender melhor as operações matemáticas. Vou dividir o projeto em módulos e fornecer exemplos de código para cada parte.

### Módulo 1: Estrutura Básica
Primeiro, definimos a estrutura básica do programa, que inclui a função `main` e a leitura de entrada do usuário.

```c
#include <stdio.h>

int main() {
    double num1, num2;
    char operador;

    printf("Digite a operação no formato: número operador número\\n");
    scanf("%lf %c %lf", &num1, &operador, &num2);

    // Continuação do código...
    return 0;
}
```

### Módulo 2: Realizando Operações Aritméticas
Aqui, implementamos as operações aritméticas básicas usando uma estrutura `switch`.

```c
switch(operador) {
    case '+':
        printf("%.2lf + %.2lf = %.2lf\\n", num1, num2, num1 + num2);
        break;
    case '-':
        printf("%.2lf - %.2lf = %.2lf\\n", num1, num2, num1 - num2);
        break;
    case '*':
        printf("%.2lf * %.2lf = %.2lf\\n", num1, num2, num1 * num2);
        break;
    case '/':
        if(num2 != 0.0)
            printf("%.2lf / %.2lf = %.2lf\\n", num1, num2, num1 / num2);
        else
            printf("Divisão por zero!\\n");
        break;
    default:
        printf("Operador inválido.\\n");
}
```

### Módulo 3: Operações Avançadas (Opcional)
Para uma calculadora no padrão "programador", você pode adicionar operações como binário para decimal, decimal para binário, etc.

```c
// Função para converter de binário para decimal
int binarioParaDecimal(int binario) {
    int decimal = 0, base = 1, rem;
    while (binario > 0) {
        rem = binario % 10;
        decimal = decimal + rem * base;
        binario = binario / 10 ;
        base = base * 2;
    }
    return decimal;
}

// Exemplo de uso dentro da função main
int numBinario;
printf("Digite um número binário para converter para decimal:\\n");
scanf("%d", &numBinario);
printf("Decimal: %d\\n", binarioParaDecimal(numBinario));
```

Lembre-se de testar cada módulo individualmente antes de integrá-los para garantir que cada parte funcione corretamente. Além disso, considere tratar possíveis erros de entrada para tornar seu programa mais robusto. Espero que esses exemplos ajudem a quem precisa começar seu projeto de calculadora em C.
