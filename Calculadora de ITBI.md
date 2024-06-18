//Sistema Calculadora de ITBI


//importa a classe JOptionPane que será utilizada para exibir caixas de diálogo.
import javax.swing.JOptionPane;

public class ITBI {

    public static void main(String[] args) {
    
//Recebe valor de transação do imóvel

        String valortransacaostring = JOptionPane.showInputDialog("Digite o valor de transação do imóvel:");
        double valortransacao = Double.parseDouble(valortransacaostring);

//Recebe valor venal do imóvel

        String valorvenalstring = JOptionPane.showInputDialog("Digite o valor venal do imóvel:");
        double valorvenal = Double.parseDouble(valorvenalstring);

//Recebe porcentagem do imposto ITBI

        String porcentagemitbistring = JOptionPane.showInputDialog("Digite a porcentagem do imposto ITBI:");
        double porcentagemitbi = Double.parseDouble(porcentagemitbistring);

//Calcula o maior valor entre o valor de transação e o valor vena

        double maiorvalor = Math.max(valortransacao, valorvenal);

//Calcula valor do imposto ITBI

        double valorimposto = (porcentagemitbi / 100) * maiorvalor;

//Exibi o valor do imposto calculado

        JOptionPane.showMessageDialog(null, "O valor do ITBI é: R$ " + String.format("%.2f", valorimposto));
    }
}