<div align="center">

## Editor in Java


</div>

### Description

Learn basics of file handling,JFileChooser swing utility and now u have simple!!!!! editor

Please rate me as it is my first attempt

An assignment in my college
 
### More Info
 
it is basic code for editor with UI and u can go through and learn.

then u can add anything to make it a mini project in second year


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[SHRIDHAR VISHWAS PURANDARE](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/shridhar-vishwas-purandare.md)
**Level**          |Beginner
**User Rating**    |4.4 (22 globes from 5 users)
**Compatibility**  |Java \(JDK 1\.5\)
**Category**       |[Files/ File Controls/ Input/ Output](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/files-file-controls-input-output__2-58.md)
**World**          |[Java](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/java.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/shridhar-vishwas-purandare-editor-in-java__2-5044/archive/master.zip)





### Source Code

```
/*
*
*  @AUTHOR -- SHRIDHAR PURANDARE
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;
import javax.swing.event.*;
import javax.swing.filechooser.*;
import java.io.*;
public class win extends Frame implements WindowListener
{
			public Frame ob1;
			public MenuBar ob2;
			public Menu file;
			public MenuItem New;
			public MenuItem Open;
			public MenuItem Save;
			public TextArea text;
			BufferedReader inputStream;
			public File filename;
			public FileWriter outputStream;
		public win()
		{
			ob1=new Frame("Darshan");
			ob1.setLayout(new BorderLayout(10,20));
			ob1.resize(200,200);
			ob2=new MenuBar();
			ob1.setMenuBar(ob2);
			file=new Menu("File");
			New=new MenuItem("New");
			Open=new MenuItem("Open");
			Save=new MenuItem("Save");
			file.add(New);
			New.addActionListener(new ActionListener()
			{
				public void actionPerformed(ActionEvent event)
				{
					int ask = JOptionPane.showConfirmDialog(win.this,"Are you sure? This will lose any unsaved documents!");
					if (ask ==JOptionPane.YES_OPTION)
						{
 							text.setText("");
						}
				setTitle("dar");
				}
			});// end actionlistener of menuitem New
			file.insertSeparator(1);
			file.add(Open);
			Open.addActionListener(new ActionListener()
			{
				public void actionPerformed(ActionEvent event)
					{
						openfile();
					}
			});
			file.insertSeparator(3);
			file.add(Save);
			Save.addActionListener(new ActionListener()
			{
				public void actionPerformed(ActionEvent event)
				{
					saveFile();
				}
			});
			text=new TextArea();
			ob1.add(text);
			ob2.add(file);
			ob1.addWindowListener(this);
			ob1.show();
		}
	public static void main(String[] args)
	{
		//System.out.println("Hello World!");
		win ob3=new win();
	}
	 public void windowClosing(WindowEvent e) {
		System.exit(0);
	}
	public void windowActivated(WindowEvent e) {}
	public void windowDeactivated(WindowEvent e) {}
	public void windowDeiconified(WindowEvent e) {}
	public void windowIconified(WindowEvent e) {}
	public void windowOpened(WindowEvent e) {}
	public void windowClosed(WindowEvent e) {}
	private void openfile()
{
	JFileChooser filechooser=new JFileChooser();
	filechooser.setFileSelectionMode(JFileChooser.FILES_ONLY);
	int result=filechooser.showOpenDialog(this);
	if(result==JFileChooser.CANCEL_OPTION)
	return;
	filename=filechooser.getSelectedFile();
	if(filename==null||filename.getName().equals(""))
JOptionPane.showMessageDialog(this,"invalid filename" ,"invalid filename",JOptionPane.ERROR_MESSAGE);
try {
     inputStream = new BufferedReader(new FileReader(filename.getPath()));
     String inputLine;
     text.setText("");
     setTitle("Darshan Notepad-"+filename.getName());
     while((inputLine = inputStream.readLine()) != null) {
       text.append(inputLine+"\n");
     }
    }
    catch(FileNotFoundException ioe) {
     JOptionPane.showMessageDialog(null, "Sorry,File Not Found", "", JOptionPane.WARNING_MESSAGE );
    }
    catch(IOException ioe) {
     System.out.println(filename.getAbsoluteFile());
    }
}
		private void saveFile()
		{
			JFileChooser ob=new JFileChooser();
			ob.setFileSelectionMode(JFileChooser.FILES_ONLY);
			int flag=ob.showSaveDialog(this);
			if(flag==JFileChooser.CANCEL_OPTION)
				return;
			filename=ob.getSelectedFile();
			if(filename==null|filename.getName().equals(""))
				JOptionPane.showMessageDialog(null,"Invalid filename","Invalid filename",JOptionPane.ERROR_MESSAGE);
			try
			{
				 outputStream=new FileWriter(filename.getPath());
     setTitle("darshan Notepad-"+filename.getName());
     outputStream.write(text.getText());
     outputStream.close();
    }
    catch(IOException ioe) {
      System.out.println("IOException");
    }
}
}
```

