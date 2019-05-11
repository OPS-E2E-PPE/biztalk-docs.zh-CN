---
title: 第 2 课：创建 swift 架构项目的强名称的 BizTalk 程序集 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- assemblies, creating strong-names
- strong-named assemblies
ms.assetid: 2aacbf38-8b1d-46ea-89ae-5207327bedc1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 98739cfa16aa519bc67ca5a4c2b5dfa5bd2af371
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530350"
---
# <a name="lesson-2-creating-a-strong-named-biztalk-assembly-for-the-swiftschemas-project"></a><span data-ttu-id="ff367-102">第 2 课：创建 swift 架构项目的强名称的 BizTalk 程序集</span><span class="sxs-lookup"><span data-stu-id="ff367-102">Lesson 2: Creating a Strong-Named BizTalk Assembly for the SWIFTSchemas Project</span></span>
<span data-ttu-id="ff367-103">在本课程中，您创建强名称对其编译并部署 BizTalk 程序集。</span><span class="sxs-lookup"><span data-stu-id="ff367-103">In this lesson, you create a strong name upon which the BizTalk assemblies are compiled and deployed.</span></span> <span data-ttu-id="ff367-104">强名称的程序集提供了多个安全优势：</span><span class="sxs-lookup"><span data-stu-id="ff367-104">A strong-named assembly provides several security benefits:</span></span>  
  
- <span data-ttu-id="ff367-105">强名称通过分配的数字签名和唯一的密钥对保证唯一性的程序集。</span><span class="sxs-lookup"><span data-stu-id="ff367-105">A strong name guarantees the uniqueness of the assembly by assigning a digital signature and a unique key pair.</span></span>  
  
- <span data-ttu-id="ff367-106">强名称保护通过确保任何其他人可以生成的程序集的后续版本的程序集的沿袭。</span><span class="sxs-lookup"><span data-stu-id="ff367-106">A strong name protects the lineage of the assembly by ensuring that no one else can generate a subsequent version of the assembly.</span></span>  
  
- <span data-ttu-id="ff367-107">强名称提供可靠的完整性检查，以保证，最后一次生成之后未更改过的程序集的内容。</span><span class="sxs-lookup"><span data-stu-id="ff367-107">A strong name provides a strong integrity check to guarantee that the contents of the assembly have not changed since the last build.</span></span>  
  
  <span data-ttu-id="ff367-108">可以使用附带的强名称工具 (sn.exe) 来生成密钥文件[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]或[!INCLUDE[btsDotNetFramework](../../includes/btsdotnetframework-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ff367-108">You can generate a key file by using the strong name tool (sn.exe) that comes with [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] or the [!INCLUDE[btsDotNetFramework](../../includes/btsdotnetframework-md.md)].</span></span>  
  
### <a name="to-create-a-strong-named-biztalk-assembly"></a><span data-ttu-id="ff367-109">若要创建的强名称的 BizTalk 程序集</span><span class="sxs-lookup"><span data-stu-id="ff367-109">To create a strong-named BizTalk assembly</span></span>  
  
1. <span data-ttu-id="ff367-110">启动 Visual Studio 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="ff367-110">Start Visual Studio command prompt.</span></span>  
  
2. <span data-ttu-id="ff367-111">在 Visual Studio 命令提示符下，浏览到\<*驱动器*\>: \labs 文件夹。</span><span class="sxs-lookup"><span data-stu-id="ff367-111">At the Visual Studio command prompt, browse to the \<*drive*\>:\labs folder.</span></span>  
  
3. <span data-ttu-id="ff367-112">在命令提示符处，键入**sn – k swift.snk**，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="ff367-112">At the command prompt, type **sn –k swift.snk**, and then press ENTER.</span></span> <span data-ttu-id="ff367-113">确保在输出窗口中显示一条成功消息。</span><span class="sxs-lookup"><span data-stu-id="ff367-113">Ensure that a success message appears in the output window.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ff367-114">如果未显示正确的消息，使用 Visual Studio 来解决您的程序集。</span><span class="sxs-lookup"><span data-stu-id="ff367-114">If the correct message does not appear, use Visual Studio to troubleshoot your assembly.</span></span>  
  
4. <span data-ttu-id="ff367-115">在解决方案资源管理器中右键单击**swift 架构**项目，并单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="ff367-115">In Solution Explorer, right-click the **SWIFTSchemas** project, and then click **Properties**.</span></span>  
  
5. <span data-ttu-id="ff367-116">在 swift 架构属性页对话框中，确保**常见属性**扩展，并选择**程序集**。</span><span class="sxs-lookup"><span data-stu-id="ff367-116">In the SWIFTSchemas Property Pages dialog box, ensure that **Common Properties** is expanded, and then select **Assembly**.</span></span>  
  
6. <span data-ttu-id="ff367-117">向下的程序集属性在右窗格中，在滚动**强名称**部分中，单击右侧的框中**程序集密钥文件**。</span><span class="sxs-lookup"><span data-stu-id="ff367-117">Scroll down the assembly properties in the right pane, and in the **Strong name** section, click the box to the right of **Assembly Key File**.</span></span> <span data-ttu-id="ff367-118">单击省略号按钮。</span><span class="sxs-lookup"><span data-stu-id="ff367-118">Click the ellipsis button.</span></span>  
  
7. <span data-ttu-id="ff367-119">在程序集密钥文件对话框中，浏览到 **\<*驱动器*:\>\labs**。</span><span class="sxs-lookup"><span data-stu-id="ff367-119">In the Assembly Key File dialog box, browse to **\<*drive*:\>\labs**.</span></span>  
  
8. <span data-ttu-id="ff367-120">选择**swift.snk**文件作为密钥文件，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="ff367-120">Select the **swift.snk** file as the key file, and then click **Open**.</span></span>  
  
9. <span data-ttu-id="ff367-121">在 swift 架构属性页对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ff367-121">In the SWIFTSchemas Property Pages dialog box, click **OK**.</span></span>  
  
10. <span data-ttu-id="ff367-122">上**文件**菜单上，单击**全部保存**以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="ff367-122">On the **File** menu, click **Save All** to save your changes.</span></span>  
  
    <span data-ttu-id="ff367-123">请继续执行[第 3 课：将 SWIFT 架构添加到项目](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-swift-schemas-to-a-project.md)。</span><span class="sxs-lookup"><span data-stu-id="ff367-123">Proceed to [Lesson 3: Adding SWIFT Schemas to a Project](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-swift-schemas-to-a-project.md).</span></span>