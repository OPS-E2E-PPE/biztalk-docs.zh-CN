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
# <a name="generate-wsdl-with-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="7209f-102">生成 WSDL 与 WCF LOB 适配器 SDK</span><span class="sxs-lookup"><span data-stu-id="7209f-102">Generate WSDL with the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="7209f-103">在开发的适配器，或从 LOB 系统更改返回的元数据，通常是有用的若要查看从适配器以验证你的操作的元数据将生成返回 Web Services 描述语言 (WSDL) 期间正确。</span><span class="sxs-lookup"><span data-stu-id="7209f-103">During development of an adapter, or when the metadata that is returned from the LOB system changes, it is often useful to view the Web Services Description Language (WSDL) that is returned from the adapter to verify that the metadata for your operations is generated correctly.</span></span> <span data-ttu-id="7209f-104">有几种方法来生成的 WSDL。</span><span class="sxs-lookup"><span data-stu-id="7209f-104">There are several methods to generate the WSDL.</span></span> <span data-ttu-id="7209f-105">本主题提供有关使用 svcutil.exe 和元数据搜索浏览控件的信息。</span><span class="sxs-lookup"><span data-stu-id="7209f-105">This topic provides information about using svcutil.exe and the Metadata Search Browse control.</span></span>  

  
## <a name="use-svcutilexe"></a><span data-ttu-id="7209f-106">使用 svcutil.exe</span><span class="sxs-lookup"><span data-stu-id="7209f-106">Use svcutil.exe</span></span>  
 <span data-ttu-id="7209f-107">Svcutil.exe 是随 Windows SDK 接受 URL 和可选的交换机，并返回 WSDL 提供一个命令行实用工具。</span><span class="sxs-lookup"><span data-stu-id="7209f-107">Svcutil.exe is a command-line utility shipped with the Windows SDK that accepts a URL and optional switches, and returns WSDL.</span></span> <span data-ttu-id="7209f-108">下面是使用 svcutil.exe 要返回的 WSDL Echo 适配器的示例：</span><span class="sxs-lookup"><span data-stu-id="7209f-108">The following is an example of using svcutil.exe to return the WSDL of the Echo Adapter:</span></span>  
  
 ```
 Svcutil.exe “echov2://lobhostname/lobapplication?enableAuthentication=False” /target:metadata
 ```
  
 <span data-ttu-id="7209f-109">这将另存为 Microsoft.Adapters.Samples.Echov2.wsdl 的元数据。</span><span class="sxs-lookup"><span data-stu-id="7209f-109">This saves the metadata as Microsoft.Adapters.Samples.Echov2.wsdl.</span></span> <span data-ttu-id="7209f-110">如果你的适配器具有许多操作，你可以选择返回所需的操作通过使用操作 = OperationName 作为 URI 的一部分。</span><span class="sxs-lookup"><span data-stu-id="7209f-110">If your adapter has many operations, you can choose to return only the desired operations by using ‘op=OperationName’ as part of the URI.</span></span> <span data-ttu-id="7209f-111">下面是使用这返回仅 EchoStrings 信息的示例：</span><span class="sxs-lookup"><span data-stu-id="7209f-111">The following is an example of using this to return only the EchoStrings information:</span></span>  
  
```  
SvcUtil.exe “echov2://lobhostname/lobapplication?enableAuthentication=False&op=Echo/EchoStrings” /target:metadata  
```  
  
## <a name="use-the-metadata-search-browse-control"></a><span data-ttu-id="7209f-112">使用元数据搜索浏览控件</span><span class="sxs-lookup"><span data-stu-id="7209f-112">Use the Metadata Search Browse Control</span></span>  
 <span data-ttu-id="7209f-113">元数据搜索浏览控件是一个 Windows 控件，在包含在向导中使用[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7209f-113">The Metadata Search Browse control is a Windows control that is used in the wizards included in [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="7209f-114">你可以将此控件添加到 Visual Studio 中的任何 Windows 窗体项目和使用它来选择你的适配器，所需的操作，然后生成的 WSDL。</span><span class="sxs-lookup"><span data-stu-id="7209f-114">You can add this control to any Windows Forms project in Visual Studio, and use it to select your adapter, the desired operations, and then generate the WSDL.</span></span>  
  
1.  <span data-ttu-id="7209f-115">打开[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]命令提示符。</span><span class="sxs-lookup"><span data-stu-id="7209f-115">Open a [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] command prompt.</span></span>  
  
2.  <span data-ttu-id="7209f-116">上**文件**菜单上，选择**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="7209f-116">On the **File** menu, select **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="7209f-117">在**新项目**对话框中，选择**Windows 应用程序**从**模板**。</span><span class="sxs-lookup"><span data-stu-id="7209f-117">In the **New Project** dialog box, select **Windows Application** from **Templates**.</span></span> <span data-ttu-id="7209f-118">输入项目名称，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="7209f-118">Enter a project name, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="7209f-119">打开**工具箱**，展开**公共控件**，右键单击**工具箱**，然后单击**选择项**。</span><span class="sxs-lookup"><span data-stu-id="7209f-119">Open the **Toolbox**, expand **Common Controls**, right-click the **Toolbox**, and then click **Choose Items**.</span></span>  
  
5.  <span data-ttu-id="7209f-120">在**选择工具箱项**对话框中，查找**MetadataUserControl**上**.NET Framework 组件**选项卡上，选择此项目旁边的复选框，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="7209f-120">In the **Choose Toolbox Items** dialog box, find **MetadataUserControl** on the **.NET Framework Components** tab, select the check box beside this item, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="7209f-121">从工具箱中，将 MetadataUserControl 拖到 form1。</span><span class="sxs-lookup"><span data-stu-id="7209f-121">From the Toolbox, drag the MetadataUserControl to Form1.</span></span> <span data-ttu-id="7209f-122">你可能需要调整窗体以查看整个控件的大小。</span><span class="sxs-lookup"><span data-stu-id="7209f-122">You may need to resize the form to see the entire control.</span></span> <span data-ttu-id="7209f-123">你应能够现在运行项目，并验证该控件可正常运行，从而允许您选择适配器和操作。</span><span class="sxs-lookup"><span data-stu-id="7209f-123">You should be able to run the project now and verify that the control is functional, allowing you to select an adapter and operations.</span></span>  
  
7.  <span data-ttu-id="7209f-124">若要使用此控件中生成 WSDL，必须将代码添加到窗体调用**GetWsdl**此控件的方法。</span><span class="sxs-lookup"><span data-stu-id="7209f-124">To generate WSDL by using this control, you must add code to your form to call the **GetWsdl** method of this control.</span></span> <span data-ttu-id="7209f-125">下面的示例演示如何调用**GetWsdl**并将数据保存到文件：</span><span class="sxs-lookup"><span data-stu-id="7209f-125">The following example demonstrates how to call **GetWsdl** and save the data to file:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7209f-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7209f-126">See Also</span></span>  
 [<span data-ttu-id="7209f-127">解决使用 WCF LOB 适配器 SDK 创建的适配器</span><span class="sxs-lookup"><span data-stu-id="7209f-127">Troubleshoot adapter created using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/troubleshoot-adapter-created-using-the-wcf-lob-adapter-sdk.md)