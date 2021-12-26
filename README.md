package Toko;
import java.text.NumberFormat;
import java.util.StringTokenizer;
import java.util.Locale;

public class FormTransaksi extends javax.swing.JFrame {

   
    public FormTransaksi() {
        initComponents();
    }
    publik StringTokenizer token;
    publik String gantiformat="";
    publik String nm_barang="";
    publik long harga_brg;
    publik int jml_beli;
    publik long jumlah_brg;
    publik long kembalian;
    publik long jumlahbyr;
                              
    private void jButton3ActionPerformed(java.awt.event.ActionEvent evt) {                                         
        this.dispose();
    }                                        

    private void CBNamaBrgActionPerformed(java.awt.event.ActionEvent evt) {                                          
        nm_barang=(String)CBNamaBrg.getSelectedItem();
        if(nm_barang=="Televisi")
        {
            harga_brg=2500000;
        }else if(nm_barang=="Speaker")
        {
            harga_brg=1250000;

        }else if(nm_barang=="Kulkas")
        {
            harga_brg=2800000;
        }
        gantiformat=NumberFormat.getNumberInstance(Locale.ENGLISH).format(harga_brg);
        token=new StringTokenizer(gantiformat,",");
        gantiformat=token.nextToken();
        gantiformat=gantiformat.replace(',','.');
        TxtHargaBarang.setText(gantiformat);
                                    
    }                                         

    private void jButton1ActionPerformed(java.awt.event.ActionEvent evt) {                                         
       
        jml_beli=Integer.parseInt(TxtJbeli.getText());

        jumlah_hrg=jml_beli*harga_brg;

        gantiformat=NumberFormat.getNumberInstance(Locale.ENGLISH).format(jumlah_hrg);
        token=new StringTokenizer(gantiformat,",");
        gantiformat=token.nextToken();
        gantiformat=gantiformat.replace(',','.');
        TxtJmlHarga.setText(gantiformat);            
    }                                        

    private void jButton2ActionPerformed(java.awt.event.ActionEvent evt) {                                         
        CBNamaBrg.setSelectedIndex(-1);
        TxtHargaBarang.setText("");
        TxtJbeli.setText("");
        TxtJmlBayar.setText("");
        TxtJmlHarga.setText("");
        TxtJmlkembalian.setText("");

           
    }                                        

    private void TxtJmlBayarActionPerformed(java.awt.event.ActionEvent evt) {                                            
        jumlahbyr=Long.parseLong(TxtJmlBayar.getText());

        kembalian=jumlahbyr-jumlah_hrg;

        gantiformat=NumberFormat.getNumberInstance(Locale.ENGLISH).format(jumlahbyr);
        token=new StringTokenizer(gantiformat,",");
        gantiformat=token.nextToken();
        gantiformat=gantiformat.replace(',','.');
        TxtJmlBayar.setText(gantiformat);

        gantiformat=NumberFormat.getNumberInstance(Locale.ENGLISH).format(kembalian);
        token=new StringTokenizer(gantiformat,",");
        gantiformat=token.nextToken();
        gantiformat=gantiformat.replace(',','.');
        TxtJmlkembalian.setText(gantiformat);
      
    }                                           

   
    public static void main(String args[]) {
       
        java.awt.EventQueue.invokeLater(new Runnable() {
            public void run() {
                new FormTransaksi().setVisible(true);
            }
        });
    }

    // Variables declaration - do not modify                     
    private javax.swing.JComboBox<String> CBNamaBrg;
    private javax.swing.JTextField TxtHargaBarang;
    private javax.swing.JTextField TxtJbeli;
    private javax.swing.JTextField TxtJmlBayar;
    private javax.swing.JTextField TxtJmlHarga;
    private javax.swing.JTextField TxtJmlkembalian;
    private javax.swing.JButton jButton1;
    private javax.swing.JButton jButton2;
    private javax.swing.JButton jButton3;
    private javax.swing.JLabel jLabel1;
    private javax.swing.JLabel jLabel2;
    private javax.swing.JLabel jLabel3;
    private javax.swing.JLabel jLabel4;
    private javax.swing.JLabel jLabel5;
    private javax.swing.JLabel jLabel6;
    // End of variables declaration                   
}


