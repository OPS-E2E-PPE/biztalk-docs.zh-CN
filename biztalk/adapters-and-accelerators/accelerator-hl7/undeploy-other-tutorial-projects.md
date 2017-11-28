---
title: "取消部署其他教程的项目 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5fce837f-1853-4d5d-a680-8ae2a974c750
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b00e829ad569790b257e1d5f0c16290cca68d176
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="undeploy-other-tutorial-projects"></a><span data-ttu-id="3c054-102">取消部署其他教程的项目</span><span class="sxs-lookup"><span data-stu-id="3c054-102">Undeploy Other Tutorial Projects</span></span>
<span data-ttu-id="3c054-103">当为 HL7 部署 BizTalk 快捷键 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 教程，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]在配置数据库 （也称为 BizTalk 管理数据库） 和全局程序集缓存中存储的教程的程序集文件。</span><span class="sxs-lookup"><span data-stu-id="3c054-103">When you deploy a BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) tutorials, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] stores the tutorial assembly files in the Configuration database (also known as the BizTalk Management database) and the global assembly cache.</span></span> <span data-ttu-id="3c054-104">如果你已运行另一个[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]教程，及已部署在该教程中创建的程序集，你可能会遇到错误时在批处理教程的三个部分中测试你的程序集。</span><span class="sxs-lookup"><span data-stu-id="3c054-104">If you have run another [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] tutorial, and deployed the assemblies that you created in that tutorial, you may encounter errors when you test your assemblies in the three parts of the Batching tutorial.</span></span> <span data-ttu-id="3c054-105">这可能是因为一次只能部署一个消息架构。</span><span class="sxs-lookup"><span data-stu-id="3c054-105">This may occur because you can only deploy one message schema at one time.</span></span>  
  
 <span data-ttu-id="3c054-106">你可以避免这些错误由你在前面的教程中部署的正在取消部署程序集。</span><span class="sxs-lookup"><span data-stu-id="3c054-106">You can avoid these errors by undeploying assemblies that you deployed in previous tutorials.</span></span> <span data-ttu-id="3c054-107">如果需要你可以重新部署的程序集更高版本。</span><span class="sxs-lookup"><span data-stu-id="3c054-107">You can re-deploy the assembly later if needed.</span></span>  
  
 <span data-ttu-id="3c054-108">在之前取消部署程序集，你需要取消登记在程序集中的业务流程。</span><span class="sxs-lookup"><span data-stu-id="3c054-108">Before undeploying an assembly, you need to unenlist orchestrations in the assembly.</span></span> <span data-ttu-id="3c054-109">你还需要删除对你想要取消部署，从你想要保留已部署的任何其他程序集的程序集的任何引用。</span><span class="sxs-lookup"><span data-stu-id="3c054-109">You also need to remove any reference to the assembly that you want to undeploy, from any other assembly that you want to keep deployed.</span></span> <span data-ttu-id="3c054-110">一种替代方法是删除之前开始另一个教程一个教程中，与关联的所有 Dll。</span><span class="sxs-lookup"><span data-stu-id="3c054-110">An alternative is to delete all DLLs associated with one tutorial, before starting another tutorial.</span></span>  
  
### <a name="to-undeploy-an-assembly"></a><span data-ttu-id="3c054-111">若要取消部署程序集</span><span class="sxs-lookup"><span data-stu-id="3c054-111">To undeploy an assembly</span></span>  
  
1.  <span data-ttu-id="3c054-112">取消登记业务流程中你想要通过单击 Visual Studio 中，BizTalk 资源管理器中的业务流程，然后单击取消部署的程序集使用**Unenlist**。</span><span class="sxs-lookup"><span data-stu-id="3c054-112">Unenlist orchestrations used in the assembly that you want to undeploy by clicking the orchestration in BizTalk Explorer of Visual Studio, and then clicking **Unenlist**.</span></span>  
  
2.  <span data-ttu-id="3c054-113">在你想要保留已部署的任何程序集，删除对你想要取消部署的程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="3c054-113">In any assembly that you want to keep deployed, remove references to assemblies that you want to undeploy.</span></span> <span data-ttu-id="3c054-114">右键单击解决方案资源管理器中的引用，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="3c054-114">Right click the reference in Solution Explorer, and then click **Remove**.</span></span>  
  
3.  <span data-ttu-id="3c054-115">打开 BizTalk 资源管理器中，右键单击你想要取消部署，然后单击该程序集**取消部署后再次**。</span><span class="sxs-lookup"><span data-stu-id="3c054-115">Open BizTalk Explorer, right-click the assembly that you want to undeploy, and then click **Undeploy**.</span></span>  
  
 <span data-ttu-id="3c054-116">有关取消部署程序集的详细信息，请参阅"正在取消部署程序集使用 BizTalk 资源管理器"中[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="3c054-116">For more information about undeploying an assembly, see "Undeploying an Assembly Using BizTalk Explorer" in [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] Help.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c054-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3c054-117">See Also</span></span>  
 [<span data-ttu-id="3c054-118">准备使用批处理教程</span><span class="sxs-lookup"><span data-stu-id="3c054-118">Preparing to Use the Batching Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-batching-tutorial.md)