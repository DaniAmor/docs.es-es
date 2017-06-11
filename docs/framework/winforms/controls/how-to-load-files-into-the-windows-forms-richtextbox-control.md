---
title: "C&#243;mo: Cargar archivos en el control RichTextBox de formularios Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "cuadros de texto, mostrar archivos"
  - "ejemplos [formularios Windows Forms], cuadros de texto"
  - "archivos .rtf, abrir en el control RichTextBox"
  - "archivos RTF, abrir en el control RichTextBox"
  - "archivos de texto, mostrar en el control RichTextBox"
  - "archivos .rtf, mostrar en el control RichTextBox"
  - "control RichTextBox [Windows Forms], abrir archivos"
  - "archivos RTF, mostrar en el control RichTextBox"
ms.assetid: c03451be-f285-4428-a71a-c41e002cc919
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Cargar archivos en el control RichTextBox de formularios Windows Forms
El control <xref:System.Windows.Forms.RichTextBox> de Windows Forms puede mostrar un archivo de texto sin formato, un archivo de texto sin formato Unicode o un archivo de formato de texto enriquecido \(RTF\). Para ello, llame al método <xref:System.Windows.Forms.RichTextBox.LoadFile%2A>. También puede usar el método <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> para cargar los datos desde una secuencia. Para obtener más información, consulta <xref:System.Windows.Forms.RichTextBox.LoadFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.  
  
### Para cargar un archivo en el control RichTextBox  
  
1.  Determine la ruta de acceso del archivo que quiere abrir con el componente <xref:System.Windows.Forms.OpenFileDialog>. Para obtener información general, vea [Información general sobre el componente OpenFileDialog](../../../../docs/framework/winforms/controls/openfiledialog-component-overview-windows-forms.md).  
  
2.  Llame al método <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> del control <xref:System.Windows.Forms.RichTextBox> especificando el archivo que se va a cargar y, si quiere, un tipo de archivo. En el siguiente ejemplo, el archivo que se va a cargar se toma de la propiedad <xref:System.Windows.Forms.FileDialog.FileName%2A> del componente <xref:System.Windows.Forms.OpenFileDialog>. Si llama al método con un nombre de archivo como único argumento, se presupondrá que el tipo de archivo es RTF. Para especificar otro tipo de archivo, llame al método con un valor de la enumeración <xref:System.Windows.Forms.RichTextBoxStreamType> como segundo argumento.  
  
     En el siguiente ejemplo, el componente <xref:System.Windows.Forms.OpenFileDialog> aparece cuando se hace clic en un botón. Después, el archivo seleccionado se abre y se muestra en el control <xref:System.Windows.Forms.RichTextBox>. En este ejemplo se presupone que un formulario tiene un botón, `btnOpenFile`.  
  
    ```vb  
    Private Sub btnOpenFile_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles btnOpenFile.Click  
         If OpenFileDialog1.ShowDialog() = DialogResult.OK Then  
           RichTextBox1.LoadFile(OpenFileDialog1.FileName, _  
              RichTextBoxStreamType.RichText)  
          End If  
    End Sub  
  
    ```  
  
    ```csharp  
    private void btnOpenFile_Click(object sender, System.EventArgs e)  
    {  
       if(openFileDialog1.ShowDialog() == DialogResult.OK)  
       {  
         richTextBox1.LoadFile(openFileDialog1.FileName, RichTextBoxStreamType.RichText);  
       }  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void btnOpenFile_Click(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          if(openFileDialog1->ShowDialog() == DialogResult::OK)  
          {  
             richTextBox1->LoadFile(openFileDialog1->FileName,  
                RichTextBoxStreamType::RichText);  
          }  
       }  
    ```  
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] y [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Coloque el siguiente código en el constructor del formulario para registrar el controlador de eventos.  
  
    ```csharp  
    this.btnOpenFile.Click += new System.EventHandler(this. btnOpenFile_Click);  
  
    ```  
  
    ```cpp  
    this->btnOpenFile->Click += gcnew   
       System::EventHandler(this, &Form1::btnOpenFile_Click);  
    ```  
  
    > [!IMPORTANT]
    >  Para ejecutar este proceso, es posible que el ensamblado necesite un nivel de privilegio concedido por la clase <xref:System.Security.Permissions.FileIOPermission?displayProperty=fullName>. Si está en un contexto de confianza parcial, es posible que el proceso produzca una excepción por falta de privilegios. Para obtener más información, consulta [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md).  
  
## Vea también  
 <xref:System.Windows.Forms.RichTextBox.LoadFile%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.RichTextBox>   
 [RichTextBox \(Control\)](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)   
 [Controles que se utilizan en formularios Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)