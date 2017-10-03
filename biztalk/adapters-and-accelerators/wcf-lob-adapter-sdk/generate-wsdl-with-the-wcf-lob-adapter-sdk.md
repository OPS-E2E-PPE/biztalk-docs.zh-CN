---
title: "生成 WSDL 与 WCF LOB 适配器 SDK |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f701d78d-b3ad-4f75-b814-e5b1f1319fb9
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f1075bbe59e15e3eeabde6c1d5c954460d1cb570
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="generate-wsdl-with-the-wcf-lob-adapter-sdk"></a>生成 WSDL 与 WCF LOB 适配器 SDK
在开发的适配器，或从 LOB 系统更改返回的元数据，通常是有用的若要查看从适配器以验证你的操作的元数据将生成返回 Web Services 描述语言 (WSDL) 期间正确。 有几种方法来生成的 WSDL。 本主题提供有关使用 svcutil.exe 和元数据搜索浏览控件的信息。  

  
## <a name="use-svcutilexe"></a>使用 svcutil.exe  
 Svcutil.exe 是随 Windows SDK 接受 URL 和可选的交换机，并返回 WSDL 提供一个命令行实用工具。 下面是使用 svcutil.exe 要返回的 WSDL Echo 适配器的示例：  
  
 ```
 Svcutil.exe “echov2://lobhostname/lobapplication?enableAuthentication=False” /target:metadata
 ```
  
 这将另存为 Microsoft.Adapters.Samples.Echov2.wsdl 的元数据。 如果你的适配器具有许多操作，你可以选择返回所需的操作通过使用操作 = OperationName 作为 URI 的一部分。 下面是使用这返回仅 EchoStrings 信息的示例：  
  
```  
SvcUtil.exe “echov2://lobhostname/lobapplication?enableAuthentication=False&op=Echo/EchoStrings” /target:metadata  
```  
  
## <a name="use-the-metadata-search-browse-control"></a>使用元数据搜索浏览控件  
 元数据搜索浏览控件是一个 Windows 控件，在包含在向导中使用[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。 你可以将此控件添加到 Visual Studio 中的任何 Windows 窗体项目和使用它来选择你的适配器，所需的操作，然后生成的 WSDL。  
  
1.  打开[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]命令提示符。  
  
2.  上**文件**菜单上，选择**新建**，然后单击**项目**。  
  
3.  在**新项目**对话框中，选择**Windows 应用程序**从**模板**。 输入项目名称，然后单击**确定**。  
  
4.  打开**工具箱**，展开**公共控件**，右键单击**工具箱**，然后单击**选择项**。  
  
5.  在**选择工具箱项**对话框中，查找**MetadataUserControl**上**.NET Framework 组件**选项卡上，选择此项目旁边的复选框，然后单击**确定**。  
  
6.  从工具箱中，将 MetadataUserControl 拖到 form1。 你可能需要调整窗体以查看整个控件的大小。 你应能够现在运行项目，并验证该控件可正常运行，从而允许您选择适配器和操作。  
  
7.  若要使用此控件中生成 WSDL，必须将代码添加到窗体调用**GetWsdl**此控件的方法。 下面的示例演示如何调用**GetWsdl**并将数据保存到文件：  
  
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
  
## <a name="see-also"></a>另请参阅  
 [解决使用 WCF LOB 适配器 SDK 创建的适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/troubleshoot-adapter-created-using-the-wcf-lob-adapter-sdk.md)