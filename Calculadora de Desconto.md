//Sistema Calculadora de Desconto


//importa a classe Scanner para facilitar a entrada de dados pelo usuário.
import java.util.Scanner;

public class Desconto {

    public static void main(String[] args) {
        
    //Criando um objeto Scanner para ler a entrada do usuário
        
        Scanner scanner = new Scanner(System.in);

    //Recebendo o valor do produto
        
        System.out.print("Digite o Valor do Produto: ");
        double valorproduto = scanner.nextDouble();

    //Recebe a porcentagem de desconto
        
        System.out.print("Digite a Porcentagem de Desconto: ");
        double porcentagemdesconto = scanner.nextDouble();

    //Calculando o valor do desconto
        double valordesconto = (porcentagemdesconto / 100) * valorproduto;

    //Calcula preço final do produto após aplicar o desconto
    
        double precofinal = valorproduto - valordesconto;

    //Exibi o valor do desconto e o preço final do produto
    
        System.out.println("Valor do Desconto: R$ " + String.format("%.2f", valordesconto));
        System.out.println("Preço Final do Produto: R$ " + String.format("%.2f", precofinal));

    //Fecha scanner
        scanner.close();
    }
}