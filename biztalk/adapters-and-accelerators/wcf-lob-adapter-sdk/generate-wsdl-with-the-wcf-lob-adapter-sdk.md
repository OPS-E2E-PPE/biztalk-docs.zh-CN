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
# <a name="generate-wsdl-with-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="ef31a-102">生成 WSDL 与 WCF LOB 适配器 SDK</span><span class="sxs-lookup"><span data-stu-id="ef31a-102">Generate WSDL with the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="ef31a-103">在开发的适配器，或从 LOB 系统更改返回的元数据，通常很有用，若要查看返回的适配器，验证是否生成您的操作的元数据从 Web 服务描述语言 (WSDL) 过程正确。</span><span class="sxs-lookup"><span data-stu-id="ef31a-103">During development of an adapter, or when the metadata that is returned from the LOB system changes, it is often useful to view the Web Services Description Language (WSDL) that is returned from the adapter to verify that the metadata for your operations is generated correctly.</span></span> <span data-ttu-id="ef31a-104">有几种方法生成的 WSDL。</span><span class="sxs-lookup"><span data-stu-id="ef31a-104">There are several methods to generate the WSDL.</span></span> <span data-ttu-id="ef31a-105">本主题提供有关使用 svcutil.exe 和元数据搜索浏览控件的信息。</span><span class="sxs-lookup"><span data-stu-id="ef31a-105">This topic provides information about using svcutil.exe and the Metadata Search Browse control.</span></span>  

  
## <a name="use-svcutilexe"></a><span data-ttu-id="ef31a-106">使用 svcutil.exe</span><span class="sxs-lookup"><span data-stu-id="ef31a-106">Use svcutil.exe</span></span>  
 <span data-ttu-id="ef31a-107">Svcutil.exe 是随 Windows SDK 接受 URL 和可选开关，并返回 WSDL 的命令行实用工具。</span><span class="sxs-lookup"><span data-stu-id="ef31a-107">Svcutil.exe is a command-line utility shipped with the Windows SDK that accepts a URL and optional switches, and returns WSDL.</span></span> <span data-ttu-id="ef31a-108">下面是使用 svcutil.exe 要返回的 WSDL Echo 适配器的示例：</span><span class="sxs-lookup"><span data-stu-id="ef31a-108">The following is an example of using svcutil.exe to return the WSDL of the Echo Adapter:</span></span>  
  
 ```
 Svcutil.exe “echov2://lobhostname/lobapplication?enableAuthentication=False” /target:metadata
 ```
  
 <span data-ttu-id="ef31a-109">这将元数据保存为 Microsoft.Adapters.Samples.Echov2.wsdl。</span><span class="sxs-lookup"><span data-stu-id="ef31a-109">This saves the metadata as Microsoft.Adapters.Samples.Echov2.wsdl.</span></span> <span data-ttu-id="ef31a-110">如果您的适配器具有很多操作，您可以选择使用返回所需的操作 op = OperationName 作为 URI 的一部分。</span><span class="sxs-lookup"><span data-stu-id="ef31a-110">If your adapter has many operations, you can choose to return only the desired operations by using ‘op=OperationName’ as part of the URI.</span></span> <span data-ttu-id="ef31a-111">下面是使用此以返回 EchoStrings 信息的示例：</span><span class="sxs-lookup"><span data-stu-id="ef31a-111">The following is an example of using this to return only the EchoStrings information:</span></span>  
  
```  
SvcUtil.exe “echov2://lobhostname/lobapplication?enableAuthentication=False&op=Echo/EchoStrings” /target:metadata  
```  
  
## <a name="use-the-metadata-search-browse-control"></a><span data-ttu-id="ef31a-112">使用元数据搜索浏览控件</span><span class="sxs-lookup"><span data-stu-id="ef31a-112">Use the Metadata Search Browse Control</span></span>  
 <span data-ttu-id="ef31a-113">元数据搜索浏览控件是在中包含的向导中使用一个 Windows 控件[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ef31a-113">The Metadata Search Browse control is a Windows control that is used in the wizards included in [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="ef31a-114">您可以将此控件添加到 Visual Studio 中的任何 Windows 窗体项目和使用它来选择您的适配器，所需的操作，然后生成的 WSDL。</span><span class="sxs-lookup"><span data-stu-id="ef31a-114">You can add this control to any Windows Forms project in Visual Studio, and use it to select your adapter, the desired operations, and then generate the WSDL.</span></span>  
  
1. <span data-ttu-id="ef31a-115">打开[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]命令提示符。</span><span class="sxs-lookup"><span data-stu-id="ef31a-115">Open a [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] command prompt.</span></span>  
  
2. <span data-ttu-id="ef31a-116">上**文件**菜单中，选择**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="ef31a-116">On the **File** menu, select **New**, and then click **Project**.</span></span>  
  
3. <span data-ttu-id="ef31a-117">在中**新的项目**对话框中，选择**Windows 应用程序**从**模板**。</span><span class="sxs-lookup"><span data-stu-id="ef31a-117">In the **New Project** dialog box, select **Windows Application** from **Templates**.</span></span> <span data-ttu-id="ef31a-118">输入项目名称，然后依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="ef31a-118">Enter a project name, and then click **OK**.</span></span>  
  
4. <span data-ttu-id="ef31a-119">打开**工具箱**，展开**公共控件**，右键单击**工具箱**，然后单击**选择项**。</span><span class="sxs-lookup"><span data-stu-id="ef31a-119">Open the **Toolbox**, expand **Common Controls**, right-click the **Toolbox**, and then click **Choose Items**.</span></span>  
  
5. <span data-ttu-id="ef31a-120">在中**选择工具箱项**对话框中，找到**MetadataUserControl**上 **.NET Framework 组件**选项卡上，选择此项旁边的复选框，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ef31a-120">In the **Choose Toolbox Items** dialog box, find **MetadataUserControl** on the **.NET Framework Components** tab, select the check box beside this item, and then click **OK**.</span></span>  
  
6. <span data-ttu-id="ef31a-121">从工具箱将 MetadataUserControl 拖到 Form1 上。</span><span class="sxs-lookup"><span data-stu-id="ef31a-121">From the Toolbox, drag the MetadataUserControl to Form1.</span></span> <span data-ttu-id="ef31a-122">您可能需要调整窗体以查看整个控件的大小。</span><span class="sxs-lookup"><span data-stu-id="ef31a-122">You may need to resize the form to see the entire control.</span></span> <span data-ttu-id="ef31a-123">可以立即运行该项目并验证控件可以正常运行，从而允许您选择了适配器和操作。</span><span class="sxs-lookup"><span data-stu-id="ef31a-123">You should be able to run the project now and verify that the control is functional, allowing you to select an adapter and operations.</span></span>  
  
7. <span data-ttu-id="ef31a-124">若要使用此控件生成 WSDL，必须将代码添加到窗体调用**GetWsdl**此控件的方法。</span><span class="sxs-lookup"><span data-stu-id="ef31a-124">To generate WSDL by using this control, you must add code to your form to call the **GetWsdl** method of this control.</span></span> <span data-ttu-id="ef31a-125">下面的示例演示如何调用**GetWsdl**并将数据保存到文件：</span><span class="sxs-lookup"><span data-stu-id="ef31a-125">The following example demonstrates how to call **GetWsdl** and save the data to file:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ef31a-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="ef31a-126">See Also</span></span>  
 [<span data-ttu-id="ef31a-127">使用 WCF LOB 适配器 SDK 创建的适配器疑难解答</span><span class="sxs-lookup"><span data-stu-id="ef31a-127">Troubleshoot adapter created using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/troubleshoot-adapter-created-using-the-wcf-lob-adapter-sdk.md)