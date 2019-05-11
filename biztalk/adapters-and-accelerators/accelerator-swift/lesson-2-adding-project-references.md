---
title: 第 2 课：添加项目引用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- references [projects]
- projects, adding references
ms.assetid: ddc2bf49-cddd-4edb-8043-870897879655
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c339baa026508cc520b96480a57e55dd6c86b915
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530360"
---
# <a name="lesson-2-adding-project-references"></a><span data-ttu-id="e5dee-102">第 2 课：添加项目引用</span><span class="sxs-lookup"><span data-stu-id="e5dee-102">Lesson 2: Adding Project References</span></span>
<span data-ttu-id="e5dee-103">使管道能够访问位于 Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll 文件中的默认运行时架构添加项目引用。</span><span class="sxs-lookup"><span data-stu-id="e5dee-103">You add project references so your pipelines can access the default runtime schemas located in the Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll file.</span></span> <span data-ttu-id="e5dee-104">此程序集文件包含标头架构已升级的属性所需的消息类型解析。</span><span class="sxs-lookup"><span data-stu-id="e5dee-104">This assembly file contains the header schema with promoted properties required for message-type resolution.</span></span>  
  
 <span data-ttu-id="e5dee-105">拆装组件添加到接收管道时供以后参考标头架构。</span><span class="sxs-lookup"><span data-stu-id="e5dee-105">You reference the header schemas later when you add the disassembly component to the receive pipeline.</span></span>  
  
### <a name="to-add-a-reference-to-the-default-swift-runtimeschemas-assembly"></a><span data-ttu-id="e5dee-106">若要添加到默认 SWIFT RuntimeSchemas 程序集的引用</span><span class="sxs-lookup"><span data-stu-id="e5dee-106">To add a reference to the default SWIFT RuntimeSchemas assembly</span></span>  
  
1.  <span data-ttu-id="e5dee-107">在解决方案资源管理器，请确保**SWIFTPipelines**扩展项目。</span><span class="sxs-lookup"><span data-stu-id="e5dee-107">In Solution Explorer, ensure that the **SWIFTPipelines** project is expanded.</span></span> <span data-ttu-id="e5dee-108">右键单击**引用**，然后单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="e5dee-108">Right-click **References**, and then click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="e5dee-109">在添加引用对话框中，单击**浏览**选项卡。</span><span class="sxs-lookup"><span data-stu-id="e5dee-109">In the Add Reference dialog box, click the **Browse** tab.</span></span>  
  
3.  <span data-ttu-id="e5dee-110">浏览到 **\<*驱动器*\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\Assemblies**。</span><span class="sxs-lookup"><span data-stu-id="e5dee-110">Browse to **\<*drive*\>:\Program Files\Microsoft BizTalk Accelerator for SWIFT\Assemblies**.</span></span>  
  
4.  <span data-ttu-id="e5dee-111">选择**Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll**文件。</span><span class="sxs-lookup"><span data-stu-id="e5dee-111">Select the **Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll** file.</span></span>  
  
5.  <span data-ttu-id="e5dee-112">单击**外**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="e5dee-112">Click **Add**, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e5dee-113">现在选择 RuntimeSchemas 程序集 (dll) 出现在 SWIFTPipelines 项目中的引用集合中。</span><span class="sxs-lookup"><span data-stu-id="e5dee-113">The RuntimeSchemas assembly (dll) that you selected now appears in the references collection in the SWIFTPipelines project.</span></span>  
  
#### <a name="to-add-a-reference-to-the-swiftpipelines-schemas-assembly"></a><span data-ttu-id="e5dee-114">若要添加 SWIFTPipelines 架构程序集的引用</span><span class="sxs-lookup"><span data-stu-id="e5dee-114">To add a reference to the SWIFTPipelines schemas assembly</span></span>  
  
1. <span data-ttu-id="e5dee-115">在解决方案资源管理器下**SWIFTPipelines**项目，右键单击**引用**，然后单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="e5dee-115">In Solution Explorer, under the **SWIFTPipelines** project, right-click **References**, and then click **Add Reference**.</span></span>  
  
2. <span data-ttu-id="e5dee-116">在添加引用对话框中，在**项目**选项卡上，单击**swift 架构**项目，然后单击**添加**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="e5dee-116">In the Add Reference dialog box, on the **Projects** tab, click the **SWIFTSchemas** project, click **Add**, and then click **OK**.</span></span>  
  
3. <span data-ttu-id="e5dee-117">上**文件**菜单上，单击**全部保存**以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="e5dee-117">On the **File** menu, click **Save All** to save your changes.</span></span>  
  
   <span data-ttu-id="e5dee-118">请继续执行[第 3 课：添加自定义接收管道](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-a-custom-receive-pipeline.md)。</span><span class="sxs-lookup"><span data-stu-id="e5dee-118">Proceed to [Lesson 3: Adding a Custom Receive Pipeline](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-a-custom-receive-pipeline.md).</span></span>