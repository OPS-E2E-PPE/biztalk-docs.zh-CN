---
title: "第 2 课： 创建 SWIFTSchemas 项目的具有强名称 BizTalk 程序集 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies, creating strong-names
- strong-named assemblies
ms.assetid: 2aacbf38-8b1d-46ea-89ae-5207327bedc1
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8ff979c7b6915f53ebc7144cf0774ab1ffb779a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="lesson-2-creating-a-strong-named-biztalk-assembly-for-the-swiftschemas-project"></a><span data-ttu-id="82a81-102">第 2 课： 创建 SWIFTSchemas 项目的具有强名称 BizTalk 程序集</span><span class="sxs-lookup"><span data-stu-id="82a81-102">Lesson 2: Creating a Strong-Named BizTalk Assembly for the SWIFTSchemas Project</span></span>
<span data-ttu-id="82a81-103">在本课程中，你可以创建强名称对其编译并部署 BizTalk 程序集。</span><span class="sxs-lookup"><span data-stu-id="82a81-103">In this lesson, you create a strong name upon which the BizTalk assemblies are compiled and deployed.</span></span> <span data-ttu-id="82a81-104">具有强名称程序集提供多种安全优势：</span><span class="sxs-lookup"><span data-stu-id="82a81-104">A strong-named assembly provides several security benefits:</span></span>  
  
-   <span data-ttu-id="82a81-105">强名称保证通过将数字签名和唯一的密钥对分配的程序集的唯一性。</span><span class="sxs-lookup"><span data-stu-id="82a81-105">A strong name guarantees the uniqueness of the assembly by assigning a digital signature and a unique key pair.</span></span>  
  
-   <span data-ttu-id="82a81-106">强名称可避免通过确保没有其他任何人可以生成程序集的后续版本的程序集的沿袭。</span><span class="sxs-lookup"><span data-stu-id="82a81-106">A strong name protects the lineage of the assembly by ensuring that no one else can generate a subsequent version of the assembly.</span></span>  
  
-   <span data-ttu-id="82a81-107">强名称提供可靠的完整性检查以确保自上次生成以来尚未更改的程序集的内容。</span><span class="sxs-lookup"><span data-stu-id="82a81-107">A strong name provides a strong integrity check to guarantee that the contents of the assembly have not changed since the last build.</span></span>  
  
 <span data-ttu-id="82a81-108">你可以使用附带的强名称工具 (sn.exe) 生成的密钥文件[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]或[!INCLUDE[btsDotNetFramework](../../includes/btsdotnetframework-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="82a81-108">You can generate a key file by using the strong name tool (sn.exe) that comes with [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] or the [!INCLUDE[btsDotNetFramework](../../includes/btsdotnetframework-md.md)].</span></span>  
  
### <a name="to-create-a-strong-named-biztalk-assembly"></a><span data-ttu-id="82a81-109">若要创建具有强名称的 BizTalk 程序集</span><span class="sxs-lookup"><span data-stu-id="82a81-109">To create a strong-named BizTalk assembly</span></span>  
  
1.  <span data-ttu-id="82a81-110">启动 Visual Studio 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="82a81-110">Start Visual Studio command prompt.</span></span>  
  
2.  <span data-ttu-id="82a81-111">在 Visual Studio 命令提示符处，浏览到\<*驱动器*\>: \labs 文件夹。</span><span class="sxs-lookup"><span data-stu-id="82a81-111">At the Visual Studio command prompt, browse to the \<*drive*\>:\labs folder.</span></span>  
  
3.  <span data-ttu-id="82a81-112">在命令提示符处，键入**sn-k swift.snk**，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="82a81-112">At the command prompt, type **sn –k swift.snk**, and then press ENTER.</span></span> <span data-ttu-id="82a81-113">确保在输出窗口中显示一条成功消息。</span><span class="sxs-lookup"><span data-stu-id="82a81-113">Ensure that a success message appears in the output window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="82a81-114">如果未显示正确的消息，请使用 Visual Studio 进行故障排除程序集。</span><span class="sxs-lookup"><span data-stu-id="82a81-114">If the correct message does not appear, use Visual Studio to troubleshoot your assembly.</span></span>  
  
4.  <span data-ttu-id="82a81-115">在解决方案资源管理器，右键单击**SWIFTSchemas**项目，，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="82a81-115">In Solution Explorer, right-click the **SWIFTSchemas** project, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="82a81-116">在 SWIFTSchemas 属性页对话框中，确保**通用属性**是展开，然后选择**程序集**。</span><span class="sxs-lookup"><span data-stu-id="82a81-116">In the SWIFTSchemas Property Pages dialog box, ensure that **Common Properties** is expanded, and then select **Assembly**.</span></span>  
  
6.  <span data-ttu-id="82a81-117">向下右窗格中，在和中的程序集属性滚动**强名称**部分中，单击右侧的框中**程序集密钥文件**。</span><span class="sxs-lookup"><span data-stu-id="82a81-117">Scroll down the assembly properties in the right pane, and in the **Strong name** section, click the box to the right of **Assembly Key File**.</span></span> <span data-ttu-id="82a81-118">单击省略号按钮。</span><span class="sxs-lookup"><span data-stu-id="82a81-118">Click the ellipsis button.</span></span>  
  
7.  <span data-ttu-id="82a81-119">在程序集密钥文件对话框中，浏览到  **\<*驱动器*:\>\labs**。</span><span class="sxs-lookup"><span data-stu-id="82a81-119">In the Assembly Key File dialog box, browse to **\<*drive*:\>\labs**.</span></span>  
  
8.  <span data-ttu-id="82a81-120">选择**swift.snk**文件作为的密钥文件，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="82a81-120">Select the **swift.snk** file as the key file, and then click **Open**.</span></span>  
  
9. <span data-ttu-id="82a81-121">在 SWIFTSchemas 属性页对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="82a81-121">In the SWIFTSchemas Property Pages dialog box, click **OK**.</span></span>  
  
10. <span data-ttu-id="82a81-122">上**文件**菜单上，单击**保存所有**以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="82a81-122">On the **File** menu, click **Save All** to save your changes.</span></span>  
  
 <span data-ttu-id="82a81-123">继续执行[第 3 课： 向项目中添加 SWIFT 架构](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-swift-schemas-to-a-project.md)。</span><span class="sxs-lookup"><span data-stu-id="82a81-123">Proceed to [Lesson 3: Adding SWIFT Schemas to a Project](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-swift-schemas-to-a-project.md).</span></span>