import java.util.ArrayList;
import java.util.List;
import java.util.Scanner;

class Cliente {
    private String nome;
    private String endereco;

    public Cliente(String nome, String endereco) {
        this.nome = nome;
        this.endereco = endereco;
    }

    public String getNome() {
        return nome;
    }

    public String getEndereco() {
        return endereco;
    }
}

public class GestaoClientesBanco {
    public static void main(String[] args) {
        List<Cliente> clientes = new ArrayList<>();
        Scanner scanner = new Scanner(System.in);

        int opcao;
        do {
            System.out.println("\n#### MENU ####");
            System.out.println("1. Cadastrar cliente");
            System.out.println("2. Listar clientes");
            System.out.println("3. Sair");
            System.out.print("Escolha uma opção: ");
            opcao = scanner.nextInt();

            switch (opcao) {
                case 1:
                    System.out.print("Digite o nome do cliente: ");
                    scanner.nextLine(); // Limpa o buffer
                    String nome = scanner.nextLine();
                    System.out.print("Digite o endereço do cliente: ");
                    String endereco = scanner.nextLine();
                    Cliente cliente = new Cliente(nome, endereco);
                    clientes.add(cliente);
                    System.out.println("Cliente cadastrado com sucesso!");
                    break;
                case 2:
                    System.out.println("\n#### CLIENTES CADASTRADOS ####");
                    for (Cliente c : clientes) {
                        System.out.println("Nome: " + c.getNome());
                        System.out.println("Endereço: " + c.getEndereco());
                        System.out.println("-----------------------");
                    }
                    break;
                case 3:
                    System.out.println("Saindo do programa...");
                    break;
                default:
                    System.out.println("Opção inválida! Tente novamente.");
            }
        } while (opcao != 3);
    }
}
