//Sistema Gerador de Tabuada

import javax.swing.JOptionPane;

public class Tabuada {

    public static void main(String[] args) {

//Solicita ao usuário que insira um número

        String numerostring = JOptionPane.showInputDialog("Digite um número para gerar a tabuada:");
        int numero = Integer.parseInt(numerostring);

//Construir a tabuada

        StringBuilder tabuada = new StringBuilder();

//Gera a tabuada de 1 a 10 usando um loop

        for (int i = 1; i <= 10; i++) {
            int resultado = numero * i;
            tabuada.append(numero).append(" x ").append(i).append(" = ").append(resultado).append("\n");
        }

        // Exibe a tabuada
        JOptionPane.showMessageDialog(null, tabuada.toString());
    }
}