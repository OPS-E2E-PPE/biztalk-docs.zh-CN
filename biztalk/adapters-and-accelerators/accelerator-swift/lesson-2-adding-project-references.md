---
title: "第 2 课： 添加项目引用 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- references [projects]
- projects, adding references
ms.assetid: ddc2bf49-cddd-4edb-8043-870897879655
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b00fc7d49024cec6f9c300444646da82069e16cc
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="lesson-2-adding-project-references"></a><span data-ttu-id="efe63-102">第 2 课： 添加项目引用</span><span class="sxs-lookup"><span data-stu-id="efe63-102">Lesson 2: Adding Project References</span></span>
<span data-ttu-id="efe63-103">你添加项目引用，以便你管道可以访问位于 Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll 文件中的默认运行时架构。</span><span class="sxs-lookup"><span data-stu-id="efe63-103">You add project references so your pipelines can access the default runtime schemas located in the Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll file.</span></span> <span data-ttu-id="efe63-104">此程序集文件包含与消息类型解析所需的提升属性的标头架构。</span><span class="sxs-lookup"><span data-stu-id="efe63-104">This assembly file contains the header schema with promoted properties required for message-type resolution.</span></span>  
  
 <span data-ttu-id="efe63-105">当将反汇编组件添加到接收管道供以后参考标头架构。</span><span class="sxs-lookup"><span data-stu-id="efe63-105">You reference the header schemas later when you add the disassembly component to the receive pipeline.</span></span>  
  
### <a name="to-add-a-reference-to-the-default-swift-runtimeschemas-assembly"></a><span data-ttu-id="efe63-106">若要添加到默认 SWIFT RuntimeSchemas 程序集的引用</span><span class="sxs-lookup"><span data-stu-id="efe63-106">To add a reference to the default SWIFT RuntimeSchemas assembly</span></span>  
  
1.  <span data-ttu-id="efe63-107">在解决方案资源管理器，确保**SWIFTPipelines**展开项目。</span><span class="sxs-lookup"><span data-stu-id="efe63-107">In Solution Explorer, ensure that the **SWIFTPipelines** project is expanded.</span></span> <span data-ttu-id="efe63-108">右键单击**引用**，然后单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="efe63-108">Right-click **References**, and then click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="efe63-109">在添加引用对话框中，单击**浏览**选项卡。</span><span class="sxs-lookup"><span data-stu-id="efe63-109">In the Add Reference dialog box, click the **Browse** tab.</span></span>  
  
3.  <span data-ttu-id="efe63-110">浏览到  **\<*驱动器*\>: files\microsoft BizTalk Accelerator for SWIFT\Assemblies * *。</span><span class="sxs-lookup"><span data-stu-id="efe63-110">Browse to **\<*drive*\>:\Program Files\Microsoft BizTalk Accelerator for SWIFT\Assemblies**.</span></span>  
  
4.  <span data-ttu-id="efe63-111">选择**Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll**文件。</span><span class="sxs-lookup"><span data-stu-id="efe63-111">Select the **Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll** file.</span></span>  
  
5.  <span data-ttu-id="efe63-112">单击**添加**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="efe63-112">Click **Add**, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="efe63-113">现在选择 RuntimeSchemas 程序集 (dll) 将出现在 SWIFTPipelines 项目中的引用集合。</span><span class="sxs-lookup"><span data-stu-id="efe63-113">The RuntimeSchemas assembly (dll) that you selected now appears in the references collection in the SWIFTPipelines project.</span></span>  
  
#### <a name="to-add-a-reference-to-the-swiftpipelines-schemas-assembly"></a><span data-ttu-id="efe63-114">若要添加对 SWIFTPipelines 架构集的引用</span><span class="sxs-lookup"><span data-stu-id="efe63-114">To add a reference to the SWIFTPipelines schemas assembly</span></span>  
  
1.  <span data-ttu-id="efe63-115">在解决方案资源管理器下**SWIFTPipelines**项目，右键单击**引用**，然后单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="efe63-115">In Solution Explorer, under the **SWIFTPipelines** project, right-click **References**, and then click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="efe63-116">在添加引用对话框中，在**项目**选项卡上，单击**SWIFTSchemas**项目中，单击**添加**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="efe63-116">In the Add Reference dialog box, on the **Projects** tab, click the **SWIFTSchemas** project, click **Add**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="efe63-117">上**文件**菜单上，单击**保存所有**以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="efe63-117">On the **File** menu, click **Save All** to save your changes.</span></span>  
  
 <span data-ttu-id="efe63-118">继续执行[第 3 课： 添加自定义接收管道](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-a-custom-receive-pipeline.md)。</span><span class="sxs-lookup"><span data-stu-id="efe63-118">Proceed to [Lesson 3: Adding a Custom Receive Pipeline](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-a-custom-receive-pipeline.md).</span></span>