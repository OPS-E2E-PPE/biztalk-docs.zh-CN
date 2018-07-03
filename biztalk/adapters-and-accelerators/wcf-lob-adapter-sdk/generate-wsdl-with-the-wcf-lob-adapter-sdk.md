---
title: 生成 WSDL 与 WCF LOB 适配器 SDK |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f701d78d-b3ad-4f75-b814-e5b1f1319fb9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eaf5ed992864c11d360baa30f35983f0082213b3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971070"
---
# <a name="generate-wsdl-with-the-wcf-lob-adapter-sdk"></a>生成 WSDL 与 WCF LOB 适配器 SDK
在开发的适配器，或从 LOB 系统更改返回的元数据，通常很有用，若要查看返回的适配器，验证是否生成您的操作的元数据从 Web 服务描述语言 (WSDL) 过程正确。 有几种方法生成的 WSDL。 本主题提供有关使用 svcutil.exe 和元数据搜索浏览控件的信息。  

  
## <a name="use-svcutilexe"></a>使用 svcutil.exe  
 Svcutil.exe 是随 Windows SDK 接受 URL 和可选开关，并返回 WSDL 的命令行实用工具。 下面是使用 svcutil.exe 要返回的 WSDL Echo 适配器的示例：  
  
 ```
 Svcutil.exe “echov2://lobhostname/lobapplication?enableAuthentication=False” /target:metadata
 ```
  
 这将元数据保存为 Microsoft.Adapters.Samples.Echov2.wsdl。 如果您的适配器具有很多操作，您可以选择使用返回所需的操作 op = OperationName 作为 URI 的一部分。 下面是使用此以返回 EchoStrings 信息的示例：  
  
```  
SvcUtil.exe “echov2://lobhostname/lobapplication?enableAuthentication=False&op=Echo/EchoStrings” /target:metadata  
```  
  
## <a name="use-the-metadata-search-browse-control"></a>使用元数据搜索浏览控件  
 元数据搜索浏览控件是在中包含的向导中使用一个 Windows 控件[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。 您可以将此控件添加到 Visual Studio 中的任何 Windows 窗体项目和使用它来选择您的适配器，所需的操作，然后生成的 WSDL。  
  
1. 打开[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]命令提示符。  
  
2. 上**文件**菜单中，选择**新建**，然后单击**项目**。  
  
3. 在中**新的项目**对话框中，选择**Windows 应用程序**从**模板**。 输入项目名称，然后依次**确定**。  
  
4. 打开**工具箱**，展开**公共控件**，右键单击**工具箱**，然后单击**选择项**。  
  
5. 在中**选择工具箱项**对话框中，找到**MetadataUserControl**上 **.NET Framework 组件**选项卡上，选择此项旁边的复选框，然后单击**确定**。  
  
6. 从工具箱将 MetadataUserControl 拖到 Form1 上。 您可能需要调整窗体以查看整个控件的大小。 可以立即运行该项目并验证控件可以正常运行，从而允许您选择了适配器和操作。  
  
7. 若要使用此控件生成 WSDL，必须将代码添加到窗体调用**GetWsdl**此控件的方法。 下面的示例演示如何调用**GetWsdl**并将数据保存到文件：  
  
   ```csharp  
   private void button1_Click(object sender, EventArgs e)  
   {  
      ServiceDescription sd = mdUserControl.GetWsdl();  
      FileStream myFileStream = new FileStream(tbWsdlFileName.Text, FileMode.OpenOrCreate, FileAccess.Write);  
      StreamWriter myStreamWriter = new StreamWriter(myFileStream);  
      sd.Write(myStreamWriter);  
      myStreamWriter.Flush();  
      myStreamWriter.Close();  
      MessageBox.Show("WSDL file " + tbWsdlFileName.Text + " is created.");  
   }  
  
   ```  
  
## <a name="see-also"></a>请参阅  
 [使用 WCF LOB 适配器 SDK 创建的适配器疑难解答](../../adapters-and-accelerators/wcf-lob-adapter-sdk/troubleshoot-adapter-created-using-the-wcf-lob-adapter-sdk.md)