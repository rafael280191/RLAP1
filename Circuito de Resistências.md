//Sistema de Circuito de Resistências

import javax.swing.JOptionPane;

public class Resistencia {

    public static void main(String[] args) {

//Recebe os valores das quatro resistências
        double[] resistencias = new double[4];
        for (int i = 0; i < 4; i++) {
            String resistenciastring = JOptionPane.showInputDialog("Digite o valor da resistência " + (i + 1) + ":");
            resistencias[i] = Double.parseDouble(resistenciastring);
        }

//Calcula a resistência equivalente
        double resistenciaequivalente = 0;
        for (double resistencia : resistencias) {
            resistenciaequivalente += resistencia;
        }

//Determina a maior e a menor resistência

        double maioreesistencia = resistencias[0];
        double menoreesistencia = resistencias[0];
        for (double resistencia : resistencias) {
            if (resistencia > maioreesistencia) {
                maioreesistencia = resistencia;
            }
            if (resistencia < menoreesistencia) {
                menoreesistencia = resistencia;
            }
        }

//Exibe os resultados
        JOptionPane.showMessageDialog(null, 
            "Resistência Equivalente: " + String.format("%.2f", resistenciaequivalente) + " ohms\n" +
            "Maior Resistência: " + String.format("%.2f", maioreesistencia) + " ohms\n" +
            "Menor Resistência: " + String.format("%.2f", menoreesistencia) + " ohms"
        );
    }
}