package logica;
import java.util.Scanner;
/**
 * 
 * @author Vinicius
 */
public class Ex30 {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        double saldo = 0.0;
        double dividaEmprestimo = 0.0;
        boolean continuar = true;

        System.out.println("--- BEM-VINDO AO BANCO TERMINAL ---");

        while (continuar) {
            try {
                // Menu de Opções
        System.out.println("\n----------------------------");
           System.out.printf("Saldo Atual: R$ %.2f | Dívida: R$ %.2f\n", saldo, dividaEmprestimo);
            System.out.println("1 - Saldo");
             System.out.println("2 - Depósito");
              System.out.println("3 - Saque");
             System.out.println("4 - Empréstimo");
            System.out.println("5 - Pagar Dívida");
           System.out.println("0 - Sair");
        System.out.print("Escolha uma opção: ");

        int escolha = Integer.parseInt(scanner.nextLine());

switch (escolha) {
case 1: // Saldo
             System.out.printf("Seu saldo disponível é: R$ %.2f\n", saldo);
break;

case 2: // Depósito
             System.out.print("Digite o valor para depósito: ");
    double dep = Double.parseDouble(scanner.nextLine());
       if (dep <= 0) throw new IllegalArgumentException("Valor deve ser positivo.");
          saldo += dep;
             System.out.println("Depósito realizado com sucesso!");
break;

  case 3: // Saque
             System.out.print("Digite o valor para saque: ");
    double saque = Double.parseDouble(scanner.nextLine());
         if (saque <= 0) throw new IllegalArgumentException("Valor deve ser positivo.");
         if (saque > saldo) {
              System.out.println("ERRO: Saldo insuficiente.");
      } else {
            saldo -= saque;
              System.out.println("Saque realizado. Retire o dinheiro.");
    }
break;

case 4: // Empréstimo
         if (dividaEmprestimo > 0) {
              System.out.println("NEGADO: Você já possui uma dívida em aberto.");
       } else {
    double limite = Math.pow(saldo, 2);
              System.out.printf("Seu limite de empréstimo (saldo²): R$ %.2f\n", limite);
              System.out.print("Quanto deseja pegar emprestado? ");
    double valorEmp = Double.parseDouble(scanner.nextLine());
         if (valorEmp <= 0) throw new IllegalArgumentException("Valor inválido.");
         if (valorEmp > limite) {
              System.out.println("NEGADO: Valor acima do limite permitido.");
      } else {
    double taxa = 1.10; // 10% de juros
                 dividaEmprestimo = valorEmp * taxa;
             saldo += valorEmp;
              System.out.printf("Aprovado! Você deverá pagar R$ %.2f no futuro.\n", dividaEmprestimo);
     }
       }
break;

case 5: // Pagar Dívida
         if (dividaEmprestimo == 0) {
               System.out.println("Você não possui dívidas pendentes.");
       } else if (saldo < dividaEmprestimo) {
               System.out.println("Saldo insuficiente para pagar a dívida total.");
       } else {
           saldo -= dividaEmprestimo;
               System.out.printf("Dívida de R$ %.2f paga! Saldo restante: R$ %.2f\n", dividaEmprestimo, saldo);
         dividaEmprestimo = 0;
      }
break;

case 0: // Sair
        continuar = false;
               System.out.println("Operação finalizada!");
break;

default:
               System.out.println("Opção inválida! Tente novamente.");
         }

         } catch (NumberFormatException e) {
                System.out.println("ERRO: Por favor, digite apenas números.");
         } catch (IllegalArgumentException e) {
                System.out.println("ERRO: " + e.getMessage());
         } catch (Exception e) {
                System.out.println("Ocorreu um erro inesperado.");
        }
      }
        scanner.close();
   }
}