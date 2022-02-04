# Enrollment-System-Java

    private void jButton2ActionPerformed(java.awt.event.ActionEvent evt) {                                         
        // DELETE
        try{
            String sql = "DELETE FROM `lists` WHERE ID= ?";
            con = DriverManager.getConnection(dataConn,username,password);
            pst = con.prepareStatement(sql);
            pst.setString(1, id.getText());
            pst.executeUpdate();
            JOptionPane.showMessageDialog(null,"Deleted successfully");
            
        }catch(SQLException | HeadlessException ex){
            JOptionPane.showMessageDialog(null, ex);
            
        }
        showdataTable();
    }      
    
    //For exit
       private JFrame frame;
    private void jButton4ActionPerformed(java.awt.event.ActionEvent evt) {                                         
        // EXIT
          frame = new JFrame("Exit");
      if (JOptionPane.showConfirmDialog(frame, "Confirm if you want to exit","Student Management Systems",
              JOptionPane.YES_NO_OPTION)==JOptionPane.YES_NO_OPTION){
          System.exit(0);
      }
        
    }          
    
    
    
    
    
    //for update
    
    private void jButton3ActionPerformed(java.awt.event.ActionEvent evt) {                                         
        // UPDATE
        try{
            String sql = "UPDATE lists SET Lastname=?,Firstname=?,Middlename=?,Age=?,Sex=?,Course=?,Address=? WHERE ID= ?";
            con = DriverManager.getConnection(dataConn,username,password);
            pst = con.prepareStatement(sql);
            
            pst.setString(1, last.getText());
            pst.setString(2, first.getText());
            pst.setString(3, mid.getText());
            pst.setString(4, age.getText());
            pst.setString(5, sex.getSelectedItem().toString());
            pst.setString(6, course.getSelectedItem().toString());
            pst.setString(7, add.getText());
            pst.setString(8, id.getText());
            pst.executeUpdate();
                JOptionPane.showMessageDialog(null,"Updated successfully");
        }catch(SQLException | HeadlessException ex){
            JOptionPane.showMessageDialog(null, ex);
        }
        showdataTable();
    }                                        
