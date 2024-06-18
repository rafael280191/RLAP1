//Sistema Calculadora de Aposentadoria


//importa a classe JOptionPane que será utilizada para exibir caixas de diálogo.
import javax.swing.JOptionPane;

public class CalculadoraAposentadoria {

    public static void main(String[] args) {
    
//Recebendo os dados do usuário

        String idadeString = JOptionPane.showInputDialog("Digite sua idade:");
        String sexo = JOptionPane.showInputDialog("Digite o sexo (M para Masculino, F para Feminino):");
        String anoscontribuicaoString = JOptionPane.showInputDialog("Digite seus Anos de Contribuição:");

//Convertendo os dados de String para o tipo adequado

        int idade = Integer.parseInt(idadeString);
        int anoscontribuicao = Integer.parseInt(anoscontribuicaoString);

//Variáveis para armazenar os critérios de aposentadoria

        int idadeaposentadoria;
        int tempocontribuicaoaposentadoria;

//Definindo os critérios baseados no sexo

        if (sexo.equalsIgnoreCase("M")) {
            idadeaposentadoria = 65;
            tempocontribuicaoaposentadoria = 35;
        } else if (sexo.equalsIgnoreCase("F")) {
            idadeaposentadoria = 62;
            tempocontribuicaoaposentadoria = 30;
        } else {
            JOptionPane.showMessageDialog(null, "Sexo INVÁLIDO. Digite 'M' para Masculino ou 'F' para Feminino.");
            return;
        }

//Verificando se pode se aposentar por idade

        boolean permiteaposentarporidade = (idade >= idadeaposentadoria) && (anoscontribuicao >= 15);

//Verificando se pode se aposentar por tempo de contribuição

        boolean permiteaposentarportempo = (anoscontribuicao >= tempocontribuicaoaposentadoria);

//Determinando a mensagem de resultado

        String mensagem;
        if (permiteaposentarporidade || permiteaposentarportempo) {
            mensagem = "Pode se Aposentar!";
        } else {
            int anosfaltantesidade = idadeaposentadoria - idade;
            int anosfaltantescontribuicao = tempocontribuicaoaposentadoria - anoscontribuicao;

            if (anosfaltantesidade > 0 && anosfaltantescontribuicao > 0) {
                mensagem = "Faltam " + anosfaltantesidade + " Anos para Atingir a Idade Mínima e " + anosfaltantescontribuicao + " anos de contribuição.";
            } else if (anosfaltantesidade > 0) {
                mensagem = "Faltam " + anosfaltantesidade + " Anos para Atingir a Idade Mínima.";
            } else {
                mensagem = "Faltam " + anosfaltantescontribuicao + " Anos de Contribuição.";
            }
        }

//resultado

        JOptionPane.showMessageDialog(null, mensagem);
    }
}