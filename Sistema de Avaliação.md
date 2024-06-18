//Sistema de Avaliação


//importa a classe JOptionPane que será utilizada para exibir caixas de diálogo.
import javax.swing.JOptionPane; 

public class Avaliacao {

public static void main(String[] args) {
        
//Recebendo as notas das provas e do trabalho utilizando JOptionPane

        String prova1String = JOptionPane.showInputDialog("Digite a nota da primeira prova :");
        String prova2String = JOptionPane.showInputDialog("Digite a nota da segunda prova :");
        String trabalhoString = JOptionPane.showInputDialog("Digite a nota do trabalho:");

        
//Conversão String para Double

        double prova1 = Double.parseDouble(prova1String);
        double prova2 = Double.parseDouble(prova2String);
        double trabalho = Double.parseDouble(trabalhoString);

        
//Calcula a média das notas

        double media = (prova1 + prova2 + trabalho) / 3;


//Resultado de Aprovado ou Reprovado

        String status;
        if (media >= 6) {
            status = "APROVADO";
        } else {
            status = "REPROVADO";
        }

//Mostra a média e o status (aprovação/reprovação)

        JOptionPane.showMessageDialog(null, "Média: " + media + "\nStatus: " + status);
    }
}