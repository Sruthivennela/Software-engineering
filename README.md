# Software-engineering
import java.awt.EventQueue; 
import javax.swing.JFrame; 
import javax.swing.JLabel; 
import javax.swing.JOptionPane; 
import java.awt.Font; 
import javax.swing.JTextField; 
import javax.swing.SpinnerNumberModel; 
import javax.swing.JSpinner; 
import javax.swing.JComboBox; 
import javax.swing.DefaultComboBoxModel; 
import javax.swing.JButton; 
import java.awt.event.ActionListener; 
import java.io.*; 
import java.awt.event.ActionEvent; 
import java.awt.Color; 
public class hotelbooking { 
private JFrame frame; 
private JTextField NameTxt; 
private JTextField Checkin; 
private JTextField Checkout; 
 
private String Name, Age, Gender, CheckinDt, CheckoutDt, 
HeadCount, RoomNo; 
boolean flag = true; 
/
 * Launch the application.
 */
public static void main(String[] args) { 
 EventQueue.invokeLater(new Runnable() { 
 public void run() { 
 try { 
 hotelbooking window = new hotelbooking(); 
 window.frame.setVisible(true); 
 } catch (Exception e) { 
 e.printStackTrace(); 
 } 
 } 
 }); 
 } 
/
 * Create the application.
 */
public hotelbooking() { 
 initialize(); 
 } 
/**
 * Initialize the contents of the frame.
 */
private void initialize() { 
 frame = new JFrame(); 
 frame.getContentPane().setFont(new Font("Tahoma", 
Font.BOLD, 18)); 
 frame.setBounds(100, 100, 884, 648); 
 frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE); 
 frame.getContentPane().setLayout(null); 
 
 JLabel lblNewLabel = new JLabel("FIVE STAR HOTEL"); 
 lblNewLabel.setFont(new Font("Tahoma", Font.BOLD, 22)); 
 lblNewLabel.setBounds(180, 45, 210, 35); 
 frame.getContentPane().add(lblNewLabel); 
 
 JLabel lblNewLabel_1 = new JLabel("Name: "); 
 lblNewLabel_1.setFont(new Font("Tahoma", Font.BOLD, 18)); 
 lblNewLabel_1.setBounds(106, 128, 72, 35); 
 frame.getContentPane().add(lblNewLabel_1); 
 
 JLabel lblNewLabel_1_1 = new JLabel("Age: "); 
 lblNewLabel_1_1.setFont(new Font("Tahoma", Font.BOLD, 
18)); 
 lblNewLabel_1_1.setBounds(109, 173, 69, 35); 
 frame.getContentPane().add(lblNewLabel_1_1); 
 
 JLabel lblNewLabel_1_2 = new JLabel("Gender: "); 
 lblNewLabel_1_2.setFont(new Font("Tahoma", Font.BOLD, 
19)); 
 lblNewLabel_1_2.setBounds(105, 226, 117, 35); 
 frame.getContentPane().add(lblNewLabel_1_2); 
 
 JLabel lblNewLabel_1_3 = new JLabel("Check-in-date: "); 
 lblNewLabel_1_3.setFont(new Font("Tahoma", Font.BOLD, 
18)); 
 lblNewLabel_1_3.setBounds(105, 271, 143, 38); 
 frame.getContentPane().add(lblNewLabel_1_3); 
 
 JLabel lblNewLabel_1_5 = new JLabel("Check-out-date: "); 
 lblNewLabel_1_5.setFont(new Font("Tahoma", Font.BOLD, 
18)); 
 lblNewLabel_1_5.setBounds(105, 319, 167, 37); 
 frame.getContentPane().add(lblNewLabel_1_5); 
 
 JLabel lblNewLabel_1_6 = new JLabel("Number of people"); 
 lblNewLabel_1_6.setFont(new Font("Tahoma", Font.BOLD, 
18)); 
 lblNewLabel_1_6.setBounds(105, 376, 167, 35); 
 frame.getContentPane().add(lblNewLabel_1_6); 
 
 JLabel lblNewLabel_1_7 = new JLabel("Room preference: "); 
 lblNewLabel_1_7.setFont(new Font("Tahoma", Font.BOLD, 
18)); 
 lblNewLabel_1_7.setBounds(105, 426, 200, 35); 
 frame.getContentPane().add(lblNewLabel_1_7); 
 
 NameTxt = new JTextField(); 
 NameTxt.setBounds(355, 122, 185, 31); 
 frame.getContentPane().add(NameTxt); 
 NameTxt.setColumns(10); 
 
 SpinnerNumberModel model3 = new
SpinnerNumberModel(0,0,100,1); 
 JSpinner AgeSpinner = new JSpinner(model3); 
 AgeSpinner.setFont(new Font("Tahoma", Font.BOLD, 18)); 
 AgeSpinner.setBounds(360, 178, 47, 31); 
 frame.getContentPane().add(AgeSpinner); 
 
 JComboBox GenderCmbbox = new JComboBox(); 
 GenderCmbbox.setModel(new DefaultComboBoxModel(new
String[] {"--", "Male", "Female", "Other"})); 
 GenderCmbbox.setBounds(360, 236, 81, 22); 
 frame.getContentPane().add(GenderCmbbox); 
 
 Checkin = new JTextField(); 
 Checkin.setColumns(10); 
 Checkin.setBounds(360, 284, 155, 20); 
 frame.getContentPane().add(Checkin); 
 
 Checkout = new JTextField(); 
 Checkout.setColumns(10); 
 Checkout.setBounds(360, 330, 155, 22); 
 frame.getContentPane().add(Checkout); 
 
 SpinnerNumberModel model1 = new
SpinnerNumberModel(0,0,5,1); 
 JSpinner HeadcountSpinner = new JSpinner(model1);

Sindhu Kl, [27-10-2022 10:37]
HeadcountSpinner.setFont(new Font("Tahoma", Font.BOLD, 
17)); 
 HeadcountSpinner.setBounds(360, 378, 54, 31); 
 frame.getContentPane().add(HeadcountSpinner); 
 
 SpinnerNumberModel model2 = new
SpinnerNumberModel(1,1,10,1); 
 JSpinner RoomprefSpinner = new JSpinner(model2); 
 RoomprefSpinner.setFont(new Font("Tahoma", Font.BOLD, 
17)); 
 RoomprefSpinner.setBounds(360, 426, 54, 31); 
 frame.getContentPane().add(RoomprefSpinner); 
 
 JButton Submitbtn = new JButton("Submit"); 
 Submitbtn.addActionListener(new ActionListener() { 
 public void actionPerformed(ActionEvent e){ 
 Name = NameTxt.getText(); 
 Age = String.valueOf(AgeSpinner.getValue()); 
 Gender = 
(String)GenderCmbbox.getSelectedItem(); 
 CheckinDt = Checkin.getText(); 
 CheckoutDt = Checkout.getText(); 
 HeadCount = 
String.valueOf(HeadcountSpinner.getValue()) ; 
 RoomNo = 
String.valueOf(RoomprefSpinner.getValue()); 
 verify(Name, Age, Gender, CheckinDt, CheckoutDt, 
HeadCount, RoomNo); 
 if(flag == true) { 
 String details = "Name: " + Name + "\n" + 
 "Age: " + Age + "\n" + 
 "Gender: " + Gender + "\n" + 
 "Check-in-Date: " + CheckinDt + 
"\n" + 
 "Check-out-Date: " + CheckoutDt
+ "\n" + 
 "Headcount: " + HeadCount + 
"\n" + 
 "Room number: " + RoomNo + 
"\n\n"; 
 JOptionPane.showMessageDialog(Submitbtn, 
details); 
 try { 
 FileWriter f = new
FileWriter("D:\\list.txt\\",true); 
 BufferedWriter bf = new
BufferedWriter(f); 
 bf.write(details); 
bf.newLine(); 
bf.close(); 
f.close(); 
 
 } catch (IOException e1) { 
 
 JOptionPane.showMessageDialog(Submitbtn, "Error"); 
 e1.printStackTrace(); 
 } 
 } 
 
 
 JOptionPane.showMessageDialog(Submitbtn, " SUCESSFULLY 
COMPLETED "); 
 } 
 private void verify(String name, String age, String 
gender, String checkinDt, String checkoutDt, 
 String headCount, String roomNo) { 
 if(Integer.parseInt(age) > 0 && 
Integer.parseInt(age) <= 100) { 
 Age = age; 
flag = true; 
 } 
 else { 
 flag = false; 
Age = null; 
 JOptionPane.showMessageDialog(Submitbtn, 
"Invalid Age, please submit the form again"); 
 } 
 
 if(Integer.parseInt(age) < 18) { 
 flag = false; 
 JOptionPane.showMessageDialog(Submitbtn, 
"You are underaged"); 
 } 
 
 if(!CheckDateFormat(checkinDt)) { 
 flag = false; 
 JOptionPane.showMessageDialog(Submitbtn, 
"Invalid Check in Date Format, make sure its DD/MM/YYYY or DD-MM YYYY"); 
 } 
 
 if(!CheckDateFormat(checkoutDt)) { 
 flag = false; 
 JOptionPane.showMessageDialog(Submitbtn, 
"Invalid Check out Date Format, make sure its DD/MM/YYYY or DD-MM YYYY"); 
 } 
 
 if(Integer.parseInt(headCount) > 5) { 
 flag = false; 
 JOptionPane.showMessageDialog(Submitbtn, 
"HeadCount Limit exceded (max = 5)"); 
 } 
 
 if(Integer.parseInt(roomNo) > 10) { 
 flag = false; 
 JOptionPane.showMessageDialog(Submitbtn, 
"Invalid Room number, there are only 10 rooms"); 
 } 
 } 
 
 private boolean CheckDateFormat(String Date) { 
 
 // DD/MM/YYYY 01-34-6789 checking 01 34 and 
6789 check 2 5 
 if((Date.charAt(2) == '/'  Date.charAt(2) == '-') 
&& (Date.charAt(5) == '/'  Date.charAt(5) == '-')) { 
 return true; 
 } 
 else { 
 return false; 
 } 
 
 } 
 }); 
 Submitbtn.setFont(new Font("Tahoma", Font.BOLD, 20)); 
 Submitbtn.setBounds(236, 504, 270, 50); 
 frame.getContentPane().add(Submitbtn); 
 
 JLabel lblNewLabel_2 = new JLabel("DD/MM/YYYY"); 
 lblNewLabel_2.setForeground(Color.GRAY); 
 lblNewLabel_2.setBounds(559, 286, 81, 14); 
 frame.getContentPane().add(lblNewLabel_2); 
 
 JLabel lblNewLabel_2_1 = new JLabel("DD/MM/YYYY"); 
 lblNewLabel_2_1.setForeground(Color.GRAY); 
 lblNewLabel_2_1.setBounds(559, 333, 81, 14); 
 frame.getContentPane().add(lblNewLabel_2_1); 
 } 
}
