---
title: 步骤 4： 创建 HeaderHelper 项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- projects, helper projects
- private process tutorial, creating helper projects
ms.assetid: 82413537-032a-4368-8d77-d024a7c83b0b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a01323dba6fba4673e4bcd2886df53d408421f9f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970790"
---
# <a name="step-4-creating-the-headerhelper-project"></a><span data-ttu-id="3574d-102">步骤 4： 创建 HeaderHelper 项目</span><span class="sxs-lookup"><span data-stu-id="3574d-102">Step 4: Creating the HeaderHelper Project</span></span>
<span data-ttu-id="3574d-103">在此步骤中，将创建 [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] 类库。</span><span class="sxs-lookup"><span data-stu-id="3574d-103">In this step, you create a [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] class library.</span></span> <span data-ttu-id="3574d-104">当专用业务流程收到传入消息时，HeaderHelper 库确定是否需要进行文档转换，如果需要，则执行该转换。</span><span class="sxs-lookup"><span data-stu-id="3574d-104">When a private process orchestration receives an incoming message, the HeaderHelper library determines whether a document conversion is required and if it is required, performs that conversion.</span></span> <span data-ttu-id="3574d-105">这使你的业务流程能够使用不同版本的 RosettaNet 实现框架 (RNIF) 文档。</span><span class="sxs-lookup"><span data-stu-id="3574d-105">This lets your orchestration work with different versions of RosettaNet Implementation Framework (RNIF) documents.</span></span> <span data-ttu-id="3574d-106">此外，当发出 3A2 响应消息时，HeaderHelper 库在传送该消息之前执行另一种文档转换。</span><span class="sxs-lookup"><span data-stu-id="3574d-106">Additionally, when a 3A2 response message is sent, the HeaderHelper library performs an additional document conversion before transmitting the message.</span></span>  
  
### <a name="to-create-the-headerhelper-project"></a><span data-ttu-id="3574d-107">创建 HeaderHelper 项目</span><span class="sxs-lookup"><span data-stu-id="3574d-107">To create the HeaderHelper project</span></span>  
  
1. <span data-ttu-id="3574d-108">在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，在解决方案资源管理器中右键单击 Contoso 解决方案，指向**添加**，然后单击**新项目**。</span><span class="sxs-lookup"><span data-stu-id="3574d-108">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], in Solution Explorer, right-click the Contoso solution, point to **Add**, and then click **New Project**.</span></span>  
  
2. <span data-ttu-id="3574d-109">在添加新项目对话框中，在项目类型窗格中，选择**Visual C#**。</span><span class="sxs-lookup"><span data-stu-id="3574d-109">In the Add New Project dialog box, in the Project Types pane, select **Visual C#**.</span></span>  
  
3. <span data-ttu-id="3574d-110">在模板窗格中选择**类库**模板。</span><span class="sxs-lookup"><span data-stu-id="3574d-110">In the Templates pane, select the **Class Library** template.</span></span>  
  
4. <span data-ttu-id="3574d-111">在中**名称**框中，键入**HeaderHelper**，然后单击**确定**创建项目。</span><span class="sxs-lookup"><span data-stu-id="3574d-111">In the **Name** box, type **HeaderHelper**, and then click **OK** to create the project.</span></span>  
  
5. <span data-ttu-id="3574d-112">在解决方案资源管理器，右键单击**Class1.cs**中的文件**HeaderHelper**项目，然后单击**重命名**，类型**HeaderHelper.cs**，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="3574d-112">In Solution Explorer, right click the **Class1.cs** file in the **HeaderHelper** project, click **Rename**, type **HeaderHelper.cs**, and then press **Enter**.</span></span>  
  
### <a name="to-create-the-helper-class"></a><span data-ttu-id="3574d-113">创建 Helper 类</span><span class="sxs-lookup"><span data-stu-id="3574d-113">To create the Helper class</span></span>  
  
1.  <span data-ttu-id="3574d-114">在解决方案资源管理器，展开**HeaderHelper**项目，然后再双击**HeaderHelper.cs**节点以打开 HeaderHelper 源文件。</span><span class="sxs-lookup"><span data-stu-id="3574d-114">In Solution Explorer, expand the **HeaderHelper** project, and then double-click the **HeaderHelper.cs** node to open the HeaderHelper source file.</span></span>  
  
2.  <span data-ttu-id="3574d-115">在源文件中键入以下代码，覆盖全部现有代码：</span><span class="sxs-lookup"><span data-stu-id="3574d-115">Type the following code into the source file, overwriting all the existing code:</span></span>  
  
    ```  
    using System;  
    using System.Xml;  
  
    namespace ContosoPriceAndAvailability  
    {  
        public class Helper  
        {  
            static public XmlDocument NormalizeHeader( XmlDocument curPip )  
            {  
                string strInput = curPip.OuterXml;  
                try  
                {  
                    XmlDocument xDoc = new XmlDocument();  
  
                    strInput = strInput.Replace("<!DOCTYPE Pip3A2PriceAndAvailabilityQuery SYSTEM \"3A2PriceAndAvailabilityQueryMessageGuideline_v1_3.dtd\"[]>",String.Empty);  
                    strInput = strInput.Replace("<Pip3A2PriceAndAvailabilityQuery>","<Pip3A2PriceAndAvailabilityQuery xmlns=\"http://schemas.microsoft.com/biztalk/btarn/2004/3A2PriceAndAvailabilityQueryMessageGuideline_v1_3.dtd\">");  
                    strInput = strInput.Replace("xml:",String.Empty);  
                    strInput = strInput.Replace("b:",String.Empty);  
                    strInput = strInput.Replace("lang:",String.Empty);  
                    strInput = strInput.Replace("ns1:",String.Empty);  
  
                    xDoc.LoadXml(strInput);  
  
                    return xDoc;  
                }  
                catch(Exception ex)  
                {  
                    System.Diagnostics.Debug.Write( ex.Message );  
                    throw ex;  
                }  
            }  
  
            static public string ReturnSCWithDocType( XmlDocument xmlDoc )  
            {  
                try  
                {  
                    string sResponse = xmlDoc.InnerXml;  
                    sResponse=sResponse.Replace("ns0:",String.Empty);  
                    xmlDoc.LoadXml(sResponse);  
                    xmlDoc.DocumentElement.RemoveAllAttributes();  
                    sResponse = xmlDoc.InnerXml;  
  
                    sResponse = sResponse.Insert(0,"<!DOCTYPE Pip3A2PriceAndAvailabilityResponse SYSTEM \"3A2PriceAndAvailabilityResponseMessageGuideline_v1_3.dtd\">");  
                    sResponse = sResponse.Replace("ns0:",String.Empty);  
                    sResponse = sResponse.Replace("b:",String.Empty);  
                    sResponse = sResponse.Replace("lang:",String.Empty);  
                    sResponse = sResponse.Replace("ns1:",String.Empty);  
  
                    return sResponse;  
                }  
                catch(Exception ex)  
                {  
                    throw ex;  
                }  
            }  
        }  
    }  
    ```  
  
3.  <span data-ttu-id="3574d-116">在“文件”  菜单上，单击“全部保存” 。</span><span class="sxs-lookup"><span data-stu-id="3574d-116">On the **File** menu, click **Save All**.</span></span>  
  
### <a name="to-create-a-strong-named-assembly-for-the-headerhelper-project"></a><span data-ttu-id="3574d-117">为 HeaderHelper 项目创建强名称程序集</span><span class="sxs-lookup"><span data-stu-id="3574d-117">To create a strong named assembly for the HeaderHelper project</span></span>  
  
1.  <span data-ttu-id="3574d-118">在解决方案资源管理器中右键单击**HeaderHelper**项目，并单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="3574d-118">In Solution Explorer, right-click the **HeaderHelper** project, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="3574d-119">在 HeaderHelper 属性页对话框中，选择**签名**HeaderHelp 属性窗格的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="3574d-119">In the HeaderHelper Property Pages dialog box, select **Signing** in the left pane of the HeaderHelp properties pane.</span></span>  
  
3.  <span data-ttu-id="3574d-120">在右窗格中，单击**为程序集签名**。</span><span class="sxs-lookup"><span data-stu-id="3574d-120">In the right pane, click **Sign the Assembly**.</span></span>  
  
4.  <span data-ttu-id="3574d-121">单击**选择强名称密钥文件**文本框中，并选择**\<浏览\>** 从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="3574d-121">Click the **Choose a strong name key file** text box, and then select **\<Browse\>** from the drop-down list.</span></span>  
  
5.  <span data-ttu-id="3574d-122">在选择文件对话框中，转到 Contoso 程序集的位置，然后双击**FabConPriceAvail.snk**。</span><span class="sxs-lookup"><span data-stu-id="3574d-122">In the Select File dialog box, move to the location of your Contoso assembly, and double-click **FabConPriceAvail.snk**.</span></span>  
  
6.  <span data-ttu-id="3574d-123">在“文件”  菜单上，单击“全部保存” 。</span><span class="sxs-lookup"><span data-stu-id="3574d-123">On the **File** menu, click **Save All**.</span></span>  
  
7.  <span data-ttu-id="3574d-124">在解决方案资源管理器，展开**HeaderHelper**项目中，展开**属性**节点，然后再双击**AssemblyInfo.cs**节点打开 AssemblyInfo.cs源文件。</span><span class="sxs-lookup"><span data-stu-id="3574d-124">In Solution Explorer, expand the **HeaderHelper** project, expand the **Properties** node, and then double-click the **AssemblyInfo.cs** node to open the AssemblyInfo.cs source file.</span></span>  
  
8.  <span data-ttu-id="3574d-125">在 AssemblyInfo.cs 源文件的 AssemblyCulture 属性后面的行中，键入以下代码：</span><span class="sxs-lookup"><span data-stu-id="3574d-125">In the AssemblyInfo.cs source file, type the following code on the line after the AssemblyCulture attribute:</span></span>  
  
    ```  
    [assembly: AssemblyKeyFile("../../../FabConPriceAvail.snk")]  
    ```  
  
9. <span data-ttu-id="3574d-126">在“文件”  菜单上，单击“全部保存” 。</span><span class="sxs-lookup"><span data-stu-id="3574d-126">On the **File** menu, click **Save All**.</span></span>  
  
### <a name="to-build-and-deploy-the-headerhelper-project"></a><span data-ttu-id="3574d-127">生成和部署 HeaderHelper 项目</span><span class="sxs-lookup"><span data-stu-id="3574d-127">To build and deploy the HeaderHelper project</span></span>  
  
1.  <span data-ttu-id="3574d-128">在解决方案资源管理器中右键单击**HeaderHelper**项目，并单击**生成**。</span><span class="sxs-lookup"><span data-stu-id="3574d-128">In Solution Explorer, right-click the **HeaderHelper** project, and then click **Build**.</span></span>  
  
2.  <span data-ttu-id="3574d-129">启动**Visual Studio 2012 命令提示符**。</span><span class="sxs-lookup"><span data-stu-id="3574d-129">Start **Visual Studio 2012 Command Prompt**.</span></span>  
  
3.  <span data-ttu-id="3574d-130">在命令提示符下，将移动到的位置**HeaderHelper**项目输出目录 （\Bin\Debug 文件夹）。</span><span class="sxs-lookup"><span data-stu-id="3574d-130">At the command prompt, move to the location of the **HeaderHelper** project output directory (the \Bin\Debug folder).</span></span>  
  
4.  <span data-ttu-id="3574d-131">在命令提示符处，键入**gacutil /if HeaderHelper.dll**然后按**Enter**安装**HeaderHelper**程序集到**全局程序集缓存**.</span><span class="sxs-lookup"><span data-stu-id="3574d-131">At the command prompt, type **gacutil /if HeaderHelper.dll** and press **Enter** to install the **HeaderHelper** assembly into the **Global Assembly Cache**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3574d-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="3574d-132">See Also</span></span>  
 [<span data-ttu-id="3574d-133">步骤 5：修改 Contoso 私有业务流程</span><span class="sxs-lookup"><span data-stu-id="3574d-133">Step 5: Modifying the Contoso Private Process Orchestration</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-5-modifying-the-contoso-private-process-orchestration.md)