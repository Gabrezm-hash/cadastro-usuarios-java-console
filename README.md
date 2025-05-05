# cadastro-usuarios-java-console
# cadastro-usuarios-java-console
import java.util.ArrayList;
import java.util.Scanner;

public class CadastroUsuarios {
    static class Usuario {
        String nome;
        int idade;

        Usuario(String nome, int idade) {
            this.nome = nome;
            this.idade = idade;
        }

        @Override
        public String toString() {
            return "Nome: " + nome + " | Idade: " + idade;
        }
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        ArrayList<Usuario> usuarios = new ArrayList<>();
        int opcao;

        do {
            System.out.println("\n--- MENU ---");
            System.out.println("1 - Cadastrar usuário");
            System.out.println("2 - Listar usuários");
            System.out.println("0 - Sair");
            System.out.print("Escolha uma opção: ");
            opcao = scanner.nextInt();
            scanner.nextLine(); // limpa o buffer

            switch (opcao) {
                case 1:
                    System.out.print("Digite o nome: ");
                    String nome = scanner.nextLine();
                    System.out.print("Digite a idade: ");
                    int idade = scanner.nextInt();
                    usuarios.add(new Usuario(nome, idade));
                    System.out.println("Usuário cadastrado com sucesso!");
                    break;
                case 2:
                    if (usuarios.isEmpty()) {
                        System.out.println("Nenhum usuário cadastrado.");
                    } else {
                        System.out.println("\n--- Lista de Usuários ---");
                        for (Usuario u : usuarios) {
                            System.out.println(u);
                        }
                    }
                    break;
                case 0:
                    System.out.println("Encerrando o programa...");
                    break;
                default:
                    System.out.println("Opção inválida.");
            }
        } while (opcao != 0);

        scanner.close();
    }
}

# Cadastro de Usuários - Java (Console)

Este é um projeto simples feito em Java que simula o cadastro de usuários em um sistema via console.

## Funcionalidades
- Cadastro de nome e idade
- Listagem dos usuários cadastrados
- Menu interativo

## Tecnologias
- Java 8 ou superior

## Como executar
Compile e execute o programa:
```bash
javac CadastroUsuarios.java
java CadastroUsuarios
