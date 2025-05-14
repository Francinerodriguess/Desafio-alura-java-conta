Desafio - Sistema de Controle de Conta
Descrição
Este projeto é um sistema simples de controle de conta bancária, onde o usuário pode consultar o saldo, transferir valores e receber valores. O sistema é desenvolvido em Java e utiliza a classe Scanner para entrada de dados.

Funcionalidades
Consultar saldo: O usuário pode verificar o saldo atual da conta.
Transferir valor: O usuário pode transferir um valor, desde que haja saldo suficiente.
Receber valor: O usuário pode adicionar um valor ao saldo da conta.
Sair: O usuário pode encerrar o programa.
Tecnologias Utilizadas
Java
....

Licença
Este projeto é de uso livre. Sinta-se à vontade para utilizá-lo e modificá-lo conforme necessário.




import java.sql.SQLOutput;
import java.util.Scanner;

public class Desafio {
    public static void main(String[] args) {
        String nome = "Francine Rodrigues";
        String tipoConta = "Corrente";
        double saldo = 3000.99;
        int opcao = 0;

        System.out.println("***************************");
        System.out.println("\nNome do cliente: " +nome);
        System.out.println("tipo conta: " + tipoConta);
        System.out.println("Saldo atual: " + saldo);
        System.out.println("\n***************************");

        String menu = """
                ** Digite sua opção **
                 1 - Consultar saldo
                 2 - Transferir valor
                 3 - Receber valor
                 4 - Sair
                
                """;
        Scanner leitura = new Scanner(System.in);

        while (opcao != 4) {
            System.out.println(menu);
            opcao = leitura.nextInt();

            if (opcao ==1){
                System.out.println("O saldo atualizado é " + saldo);
            }   else if (opcao ==2) {
                System.out.println("Qual o valor que deseja transferir");
                double valor = leitura.nextDouble();
                if (valor > saldo) {
                    System.out.println("Não há saldo para realizar a transferencia");
                } else {
                    saldo -= valor;
                    System.out.println("Novo saldo" + saldo);
                }
            } else if (opcao == 3) {
                System.out.println("Valor recebido: ");
                double valor = leitura.nextDouble();
                saldo += valor;
                System.out.println("Novo saldo: " + saldo);
            }else if (opcao != 4)
                System.out.println("Opção inválida");
           }
    }
}

