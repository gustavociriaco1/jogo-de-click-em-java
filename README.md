# jogo



import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.awt.event.MouseAdapter;
import java.awt.event.MouseEvent;
import javax.swing.ImageIcon;
import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JButton;
import java.awt.event.MouseListener;
import java.util.Random;
import javax.swing.Timer;

public class Fase1 extends JFrame implements ActionListener{
    
    public JLabel lbl_vidas;
    public JLabel lbl_contvidas;
    public JLabel lbl_contpontos;
    public JLabel lbl_pontos;
    public JLabel lbl_vilão;
    public JLabel lbl_heroi;
    public JButton btn_vida;
    public Timer timer;
    public int pontos=0,vidas=3;
    
  
 public Fase1(){
     // configuração Jframe
     setSize(800,800);
     setTitle("jogo teste");
     setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
     setLocationRelativeTo(null);
     setResizable(false);
     setLayout(null);
     
     // criar um Jlabel 
     lbl_vidas= new JLabel();
     lbl_vidas.setText("vidas");
     lbl_vidas.setSize(50,50);
     lbl_vidas.setLocation(10,10);
    // lbl_vidas.setBounds(20,10,10,10);
    add(lbl_vidas);
    // criar valor para vidas
    
    lbl_contvidas= new JLabel();
    lbl_contvidas.setText(String.valueOf(vidas));
    lbl_contvidas.setBounds(50,20,10,30);
    lbl_contvidas.setVisible(true);
    add(lbl_contvidas);
    
    lbl_pontos= new JLabel();
    lbl_pontos.setText("pontos");
    lbl_pontos.setBounds(450,10,60,10);
    lbl_pontos.setVisible(true);
    add(lbl_pontos);
    
     lbl_contpontos= new JLabel();
    lbl_contpontos.setText(String.valueOf(pontos));
    lbl_contpontos.setBounds(510,10,50,10);
    lbl_contpontos.setVisible(true);
    add(lbl_contpontos);
    lbl_heroi= new JLabel();
    lbl_heroi.setBounds(500,100,500,500);
    lbl_heroi.setIcon(new ImageIcon(getClass().getResource("heroi.png")));
    lbl_heroi.setVisible(true);
    add(lbl_heroi);
    
    lbl_vilão= new JLabel();
    lbl_vilão.setBounds(500,100,500,500);
    lbl_vilão.setIcon(new ImageIcon(getClass().getResource("figura.png")));
    lbl_vilão.setVisible(true);
    add(lbl_vilão);
    lbl_vilão.addMouseListener(new MouseAdapter(){
    @Override
     public void mouseClicked(MouseEvent e){
         ++pontos;
         
     }});
add(lbl_vilão);
timer= new Timer(1000,this);
timer.start();
     }


    


    @Override
    public void actionPerformed(ActionEvent e) {
        Random rand=new Random();
        int x=rand.nextInt(500);
        int y=rand.nextInt(500);
        int z=rand.nextInt(500);
        int w= rand.nextInt(500);
        lbl_heroi.setBounds(x,y,100,100);
        lbl_vilão.setBounds(z,w,100,100);
        
        
        
        

    }
 }

    
    
