	public void actionPerformed(ActionEvent e) {
		// TODO Auto-generated method stub
		Object o = e.getSource();
		if (o.equals(btnThem)) {
			if (validData()) {
				Sach s = revertSachFromTextfields();
				txtMess.setText("Thêm thành công!");
				updateTableData(s);
			}
		} else if (o.equals(btnXoaRong)) {
			clearTextfields();
		}
	}

  	private void clearTextfields() {
		// TODO Auto-generated method stub
		txtMaSach.setText("");
		txtTuaSach.setText("");
		txtTacGia.setText("");
		txtNamXB.setText("");
		txtNhaXB.setText("");
		txtSoTrang.setText("");
		txtDonGia.setText("");
		txtISBN.setText("");
		txtMess.setText("");
		txtMaSach.requestFocus();
	}

  	private void updateTableData(Sach s) {
		// TODO Auto-generated method stub
		tableModel.addRow(new Object[] { s.getMaSach(), s.getTuaSach(), s.getTacGia(), s.getNamXB(), s.getNhaXB(),
				s.getSoTrang(), s.getDonGia(), s.getIsbn() });
	}


  private Sach revertSachFromTextfields() {
		// TODO Auto-generated method stub
		String ma = txtMaSach.getText().trim();
		String tua = txtTuaSach.getText().trim();
		String tg = txtTacGia.getText().trim();
		int nxb = txtNamXB.getText().equals("") ? 0 : Integer.parseInt(txtNamXB.getText());
		String nXB = txtNhaXB.getText().trim();
		int st = txtSoTrang.getText().equals("") ? 0 : Integer.parseInt(txtSoTrang.getText());
		double dg = txtDonGia.getText().equals("") ? 0 : Double.parseDouble(txtDonGia.getText());
		String isbn = txtISBN.getText().trim();

		return new Sach(ma, tua, tg, nxb, nXB, st, dg, isbn);
	}


private boolean validData() {
		// TODO Auto-generated method stub
		String maSach = txtMaSach.getText().trim();
		String tuaSach = txtTuaSach.getText().trim();
		String tacGia = txtTacGia.getText().trim();
		String nam = txtNamXB.getText().trim();
		String gia = txtDonGia.getText().trim();
		String isbn = txtISBN.getText().trim();
		String soTrang = txtSoTrang.getText().trim();
  }
  
private void showMessage(String message, JTextField txt) {
		// TODO Auto-generated method stub
		txt.requestFocus();
		txtMess.setText(message);
	}
  }
