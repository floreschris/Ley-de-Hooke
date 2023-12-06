package com.project.main;

import javax.swing.JFrame;
import javax.swing.JPanel;
import javax.swing.border.EmptyBorder;
import javax.swing.JLabel;
import javax.swing.JOptionPane;
import javax.swing.SwingConstants;
import java.awt.Font;
import javax.swing.ImageIcon;
import javax.swing.JTextField;
import javax.swing.AbstractButton;
import javax.swing.ButtonGroup;
import javax.swing.JButton;
import java.awt.Color;
import java.awt.event.ActionListener;
import java.awt.event.ActionEvent;
import javax.swing.JRadioButton;

public class Ley extends JFrame {

	private JPanel contentPane;
	private JTextField txtX;
	private JTextField txtRespuestaW;
	private JTextField txtMasa;
	private JTextField txtRespuestaK;
	private JTextField txtRespuestaX;
	ButtonGroup group = new ButtonGroup();

	public void GrupoBotones(AbstractButton bt1, AbstractButton bt2, AbstractButton bt3, AbstractButton bt4) {
		group.add(bt1);
		group.add(bt2);
		group.add(bt3);
		group.add(bt4);

	}

	public Ley() {

		setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		setBounds(100, 100, 549, 808);
		contentPane = new JPanel();
		contentPane.setBorder(new EmptyBorder(5, 5, 5, 5));
		setContentPane(contentPane);
		contentPane.setLayout(null);

		JButton btnCalculo = new JButton("Calculo F");
		btnCalculo.setIcon(
				new ImageIcon("C:\\Users\\Usuario\\eclipse-workspace\\Hookie\\src\\com\\project\\imagenes\\btnF.png"));
		btnCalculo.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {

				double masa, rpta;

				try {

					masa = Double.parseDouble(txtMasa.getText());
					rpta = masa * 9.81;
					txtRespuestaW.setText(String.valueOf(rpta));

				} catch (Exception e2) {
					// TODO: handle exception
					JOptionPane.showMessageDialog(null, "Informacion invalida");
				}

			}
		});

		JButton btnCalculoK = new JButton("Calculo K");
		btnCalculoK.setIcon(
				new ImageIcon("C:\\Users\\Usuario\\eclipse-workspace\\Hookie\\src\\com\\project\\imagenes\\btnk.png"));
		btnCalculoK.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {

				double x, k, F;

				// F==K*x
				try {
					F = Double.parseDouble(txtRespuestaW.getText());
					x = Double.parseDouble(txtX.getText());
					k = F / x;
					txtRespuestaK.setText(String.valueOf(k));

				} catch (Exception e2) {
					// TODO: handle exception
					JOptionPane.showMessageDialog(null, "Informacion invalida");
				}
			}
		});

		JButton btnCalculoX = new JButton("Calculo X");
		btnCalculoX.setIcon(
				new ImageIcon("C:\\Users\\Usuario\\eclipse-workspace\\Hookie\\src\\com\\project\\imagenes\\btnX.png"));
		btnCalculoX.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				double x, k, F;

				// F==K*x
				try {

					F = Double.parseDouble(txtRespuestaW.getText());
					k = Double.parseDouble(txtRespuestaK.getText());
					x = F / k;
					txtRespuestaX.setText(String.valueOf(x));

				} catch (Exception e2) {
					// TODO: handle exception
					JOptionPane.showMessageDialog(null, "Informacion invalida");
				}
			}
		});

		JLabel lblNewLabel_1_2 = new JLabel("M");
		lblNewLabel_1_2.setForeground(new Color(0, 0, 0));
		lblNewLabel_1_2.setHorizontalAlignment(SwingConstants.CENTER);
		lblNewLabel_1_2.setFont(new Font("Monospaced", Font.BOLD, 18));
		lblNewLabel_1_2.setBounds(487, 699, 36, 45);
		contentPane.add(lblNewLabel_1_2);

		JLabel lblNewLabel_1_1 = new JLabel("N/M");
		lblNewLabel_1_1.setForeground(new Color(0, 0, 0));
		lblNewLabel_1_1.setFont(new Font("Monospaced", Font.BOLD, 18));
		lblNewLabel_1_1.setBounds(487, 650, 36, 45);
		contentPane.add(lblNewLabel_1_1);

		JLabel lblNewLabel_1 = new JLabel("N");
		lblNewLabel_1.setForeground(new Color(0, 0, 0));
		lblNewLabel_1.setFont(new Font("Monospaced", Font.BOLD, 18));
		lblNewLabel_1.setHorizontalAlignment(SwingConstants.CENTER);
		lblNewLabel_1.setBounds(487, 590, 36, 45);
		contentPane.add(lblNewLabel_1);
		btnCalculoX.setFont(new Font("Monospaced", Font.BOLD, 26));
		btnCalculoX.setBackground(new Color(244, 164, 96));
		btnCalculoX.setBounds(252, 319, 246, 45);
		contentPane.add(btnCalculoX);
		btnCalculoK.setFont(new Font("Monospaced", Font.BOLD, 26));
		btnCalculoK.setBackground(new Color(244, 164, 96));
		btnCalculoK.setBounds(252, 261, 246, 47);
		contentPane.add(btnCalculoK);
		btnCalculo.setBackground(new Color(244, 164, 96));
		btnCalculo.setFont(new Font("Monospaced", Font.BOLD, 26));
		btnCalculo.setBounds(252, 205, 246, 45);
		contentPane.add(btnCalculo);

		JLabel lblGravedad = new JLabel("Gravedad=9.81");
		lblGravedad.setHorizontalAlignment(SwingConstants.LEFT);
		lblGravedad.setFont(new Font("Monospaced", Font.BOLD, 30));
		lblGravedad.setBounds(22, 522, 263, 49);
		contentPane.add(lblGravedad);

		txtRespuestaX = new JTextField();
		txtRespuestaX.setHorizontalAlignment(SwingConstants.CENTER);
		txtRespuestaX.setFont(new Font("Monospaced", Font.BOLD, 16));
		txtRespuestaX.setColumns(10);
		txtRespuestaX.setBackground(new Color(205, 133, 63));
		txtRespuestaX.setBounds(285, 700, 199, 44);
		contentPane.add(txtRespuestaX);

		txtRespuestaK = new JTextField();
		txtRespuestaK.setHorizontalAlignment(SwingConstants.CENTER);
		txtRespuestaK.setFont(new Font("Monospaced", Font.BOLD, 16));
		txtRespuestaK.setColumns(10);
		txtRespuestaK.setBackground(new Color(205, 133, 63));
		txtRespuestaK.setBounds(285, 650, 199, 44);
		contentPane.add(txtRespuestaK);

		JLabel lblRespuestaX = new JLabel("Respuesta X");
		lblRespuestaX.setFont(new Font("Monospaced", Font.BOLD, 30));
		lblRespuestaX.setBounds(22, 700, 205, 44);
		contentPane.add(lblRespuestaX);

		JLabel lblRespuestaK = new JLabel("Respuesta K");
		lblRespuestaK.setFont(new Font("Monospaced", Font.BOLD, 30));
		lblRespuestaK.setBounds(22, 645, 205, 44);
		contentPane.add(lblRespuestaK);

		JRadioButton rbkg = new JRadioButton("Kg");
		rbkg.setBounds(332, 434, 56, 23);
		contentPane.add(rbkg);
		rbkg.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {

				double kg = Double.parseDouble(JOptionPane.showInputDialog("Ingrese la masa en Kilogramos"));
				txtMasa.setText(String.valueOf(kg));

			}
		});
		rbkg.setFont(new Font("Monospaced", Font.BOLD, 18));
		rbkg.setBackground(new Color(218, 165, 32));

		JRadioButton rbgr = new JRadioButton("Gr");
		rbgr.setBounds(424, 434, 47, 23);
		contentPane.add(rbgr);
		rbgr.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {

				double convertidor;
				double gr = Double.parseDouble(JOptionPane.showInputDialog("Ingrese la masa en Gramos"));
				convertidor = gr / 1000;
				txtMasa.setText(String.valueOf(convertidor));
			}
		});
		rbgr.setFont(new Font("Monospaced", Font.BOLD, 18));
		rbgr.setBackground(new Color(218, 165, 32));

		JLabel lblFw = new JLabel("F = W");
		lblFw.setHorizontalAlignment(SwingConstants.CENTER);
		lblFw.setFont(new Font("Monospaced", Font.BOLD, 30));
		lblFw.setBounds(291, 136, 232, 29);
		contentPane.add(lblFw);

		JLabel lblWM = new JLabel("W = M * G");
		lblWM.setHorizontalAlignment(SwingConstants.CENTER);
		lblWM.setFont(new Font("Monospaced", Font.BOLD, 30));
		lblWM.setBounds(291, 165, 242, 29);
		contentPane.add(lblWM);

		txtMasa = new JTextField();
		txtMasa.setHorizontalAlignment(SwingConstants.CENTER);
		txtMasa.setFont(new Font("Monospaced", Font.BOLD, 16));
		txtMasa.setColumns(10);
		txtMasa.setBackground(new Color(210, 105, 30));
		txtMasa.setBounds(320, 464, 164, 29);
		contentPane.add(txtMasa);

		JLabel lblMasa = new JLabel("Masa");
		lblMasa.setHorizontalAlignment(SwingConstants.LEFT);
		lblMasa.setFont(new Font("Monospaced", Font.BOLD, 28));
		lblMasa.setBounds(22, 456, 101, 36);
		contentPane.add(lblMasa);

		JRadioButton rbCm = new JRadioButton("Cm");
		rbCm.setBackground(new Color(218, 165, 32));
		rbCm.setFont(new Font("Monospaced", Font.BOLD, 18));
		rbCm.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {

				double x, cm;
				x = Integer.parseInt(JOptionPane.showInputDialog("Ingrese el alargamiento del resorte en Centimetros"));
				cm = x / 100;
				txtX.setText(String.valueOf(cm));

			}
		});
		rbCm.setBounds(424, 371, 47, 23);
		contentPane.add(rbCm);

		JRadioButton rbM = new JRadioButton("M");
		rbM.setBackground(new Color(218, 165, 32));
		rbM.setFont(new Font("Monospaced", Font.BOLD, 18));
		rbM.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {

				double x;
				x = Integer.parseInt(JOptionPane.showInputDialog("Ingrese el alargamiento del resorte en Metros"));
				txtX.setText(String.valueOf(x));

			}
		});
		rbM.setBounds(332, 371, 56, 23);
		contentPane.add(rbM);

		JLabel lblRespuestaW = new JLabel("Respuesta W");
		lblRespuestaW.setFont(new Font("Monospaced", Font.BOLD, 30));
		lblRespuestaW.setBounds(22, 582, 205, 52);
		contentPane.add(lblRespuestaW);

		JLabel lblTitke = new JLabel(
				"\uD835\uDC0B\uD835\uDC04\uD835\uDC18 \uD835\uDC1D\uD835\uDC1E \uD835\uDC07\uD835\uDC0E\uD835\uDC0E\uD835\uDC0A\uD835\uDC04");
		lblTitke.setFont(new Font("Monospaced", Font.BOLD, 50));
		lblTitke.setHorizontalAlignment(SwingConstants.CENTER);
		lblTitke.setBounds(15, 0, 483, 58);
		contentPane.add(lblTitke);

		JLabel lblX = new JLabel("X (Alargamiento)");
		lblX.setFont(new Font("Monospaced", Font.BOLD, 28));
		lblX.setBounds(22, 371, 277, 49);
		contentPane.add(lblX);

		JLabel lblFormula = new JLabel("Formula:");
		lblFormula.setForeground(new Color(0, 0, 0));
		lblFormula.setHorizontalAlignment(SwingConstants.CENTER);
		lblFormula.setFont(new Font("Monospaced", Font.BOLD, 44));
		lblFormula.setBounds(0, 62, 497, 44);
		contentPane.add(lblFormula);

		JLabel lblGif = new JLabel("");
		lblGif.setBackground(new Color(0, 0, 255));
		lblGif.setIcon(new ImageIcon(
				"C:\\Users\\Usuario\\eclipse-workspace\\Hookie\\src\\com\\project\\imagenes\\leyhooke.gif"));
		lblGif.setBounds(0, 100, 203, 264);
		contentPane.add(lblGif);

		txtX = new JTextField();
		txtX.setHorizontalAlignment(SwingConstants.CENTER);
		txtX.setBackground(new Color(210, 105, 30));
		txtX.setFont(new Font("Monospaced", Font.BOLD, 16));
		txtX.setColumns(10);
		txtX.setBounds(320, 401, 164, 26);
		contentPane.add(txtX);

		JLabel lblFkX = new JLabel("F = K.X");
		lblFkX.setBackground(Color.WHITE);
		lblFkX.setHorizontalAlignment(SwingConstants.CENTER);
		lblFkX.setFont(new Font("Monospaced", Font.BOLD, 30));
		lblFkX.setBounds(276, 96, 232, 29);
		contentPane.add(lblFkX);

		txtRespuestaW = new JTextField();
		txtRespuestaW.setHorizontalAlignment(SwingConstants.CENTER);
		txtRespuestaW.setFont(new Font("Monospaced", Font.BOLD, 16));
		txtRespuestaW.setBackground(new Color(205, 133, 63));
		txtRespuestaW.setBounds(285, 593, 199, 44);
		contentPane.add(txtRespuestaW);
		txtRespuestaW.setColumns(10);

		JLabel lblImg = new JLabel("");
		lblImg.setIcon(new ImageIcon(
				"C:\\Users\\Usuario\\eclipse-workspace\\Hookie\\src\\com\\project\\imagenes\\icons8-tidy-shelf-50.png"));
		lblImg.setBounds(22, 325, 56, 52);
		contentPane.add(lblImg);

		JLabel lblLibMundo = new JLabel("");
		lblLibMundo.setIcon(new ImageIcon(
				"C:\\Users\\Usuario\\eclipse-workspace\\Hookie\\src\\com\\project\\imagenes\\icons8-books-64.png"));
		lblLibMundo.setBounds(428, 41, 70, 65);
		contentPane.add(lblLibMundo);

		JLabel lblImgLibros = new JLabel("");
		lblImgLibros.setIcon(new ImageIcon(
				"C:\\Users\\Usuario\\eclipse-workspace\\Hookie\\src\\com\\project\\imagenes\\icons8-books-emoji-96.png"));
		lblImgLibros.setBounds(213, 109, 106, 96);
		contentPane.add(lblImgLibros);

		JLabel lblCiencia = new JLabel("");
		lblCiencia.setIcon(new ImageIcon(
				"C:\\Users\\Usuario\\eclipse-workspace\\Hookie\\src\\com\\project\\imagenes\\icons8-f\u00EDsica-96.png"));
		lblCiencia.setBounds(145, 434, 96, 77);
		contentPane.add(lblCiencia);

		JLabel lblCuaMundo = new JLabel("");
		lblCuaMundo.setIcon(new ImageIcon(
				"C:\\Users\\Usuario\\eclipse-workspace\\Hookie\\src\\com\\project\\imagenes\\icons8-global-education-64.png"));
		lblCuaMundo.setBounds(1, 41, 56, 52);
		contentPane.add(lblCuaMundo);

		JLabel lblImgMapaMundi = new JLabel("");
		lblImgMapaMundi.setIcon(new ImageIcon(
				"C:\\Users\\Usuario\\eclipse-workspace\\Hookie\\src\\com\\project\\imagenes\\icons8-globe-64.png"));
		lblImgMapaMundi.setBounds(216, 708, 70, 65);
		contentPane.add(lblImgMapaMundi);

		JLabel lblSocial = new JLabel("");
		lblSocial.setIcon(new ImageIcon(
				"C:\\Users\\Usuario\\eclipse-workspace\\Hookie\\src\\com\\project\\imagenes\\icons8-social-science-64.png"));
		lblSocial.setBounds(417, 505, 81, 77);
		contentPane.add(lblSocial);

		GrupoBotones(rbM, rbCm, rbgr, rbkg);

		JLabel lblFondo = new JLabel("");
		lblFondo.setIcon(
				new ImageIcon("C:\\Users\\Usuario\\eclipse-workspace\\Hookie\\src\\com\\project\\imagenes\\Fondo.jpg"));
		lblFondo.setBounds(0, 0, 533, 773);
		contentPane.add(lblFondo);

	}
}
