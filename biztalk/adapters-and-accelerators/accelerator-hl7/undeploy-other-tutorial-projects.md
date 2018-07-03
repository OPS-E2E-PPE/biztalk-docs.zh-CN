---
title: 取消部署其他教程项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5fce837f-1853-4d5d-a680-8ae2a974c750
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2c014a094acac4e374605cd0ebd9b9c50c9d733
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976278"
---
# <a name="undeploy-other-tutorial-projects"></a><span data-ttu-id="3fef4-102">取消部署其他教程项目</span><span class="sxs-lookup"><span data-stu-id="3fef4-102">Undeploy Other Tutorial Projects</span></span>
<span data-ttu-id="3fef4-103">当你部署 BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 的教程中，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]在配置数据库 （也称为 BizTalk 管理数据库） 和全局程序集缓存中存储的教程程序集文件。</span><span class="sxs-lookup"><span data-stu-id="3fef4-103">When you deploy a BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) tutorials, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] stores the tutorial assembly files in the Configuration database (also known as the BizTalk Management database) and the global assembly cache.</span></span> <span data-ttu-id="3fef4-104">如果您已运行另一个[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]教程，并已部署在该教程中创建的程序集，您可能会遇到错误时在批处理教程的三个部分中测试您的程序集。</span><span class="sxs-lookup"><span data-stu-id="3fef4-104">If you have run another [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] tutorial, and deployed the assemblies that you created in that tutorial, you may encounter errors when you test your assemblies in the three parts of the Batching tutorial.</span></span> <span data-ttu-id="3fef4-105">这可能是因为一次只能部署一个消息架构。</span><span class="sxs-lookup"><span data-stu-id="3fef4-105">This may occur because you can only deploy one message schema at one time.</span></span>  
  
 <span data-ttu-id="3fef4-106">您可以避免这些错误由您在前面的教程中部署的正在取消部署程序集。</span><span class="sxs-lookup"><span data-stu-id="3fef4-106">You can avoid these errors by undeploying assemblies that you deployed in previous tutorials.</span></span> <span data-ttu-id="3fef4-107">如果需要可以重新部署程序集更高版本。</span><span class="sxs-lookup"><span data-stu-id="3fef4-107">You can re-deploy the assembly later if needed.</span></span>  
  
 <span data-ttu-id="3fef4-108">在取消部署程序集之前，您需要取消登记业务流程的程序集中。</span><span class="sxs-lookup"><span data-stu-id="3fef4-108">Before undeploying an assembly, you need to unenlist orchestrations in the assembly.</span></span> <span data-ttu-id="3fef4-109">此外需要删除对你想要取消部署，从你想要保留已部署的任何其他程序集的程序集的任何引用。</span><span class="sxs-lookup"><span data-stu-id="3fef4-109">You also need to remove any reference to the assembly that you want to undeploy, from any other assembly that you want to keep deployed.</span></span> <span data-ttu-id="3fef4-110">一种替代方法是删除开始另一个教程前一个教程中，与关联的所有 Dll。</span><span class="sxs-lookup"><span data-stu-id="3fef4-110">An alternative is to delete all DLLs associated with one tutorial, before starting another tutorial.</span></span>  
  
### <a name="to-undeploy-an-assembly"></a><span data-ttu-id="3fef4-111">若要取消部署程序集</span><span class="sxs-lookup"><span data-stu-id="3fef4-111">To undeploy an assembly</span></span>  
  
1. <span data-ttu-id="3fef4-112">取消登记业务流程使用在你想要通过单击 BizTalk 浏览器中的 Visual Studio 中的业务流程，然后单击取消部署程序集中**取消登记**。</span><span class="sxs-lookup"><span data-stu-id="3fef4-112">Unenlist orchestrations used in the assembly that you want to undeploy by clicking the orchestration in BizTalk Explorer of Visual Studio, and then clicking **Unenlist**.</span></span>  
  
2. <span data-ttu-id="3fef4-113">在你想要保留已部署的任何程序集，删除你想要取消部署的程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="3fef4-113">In any assembly that you want to keep deployed, remove references to assemblies that you want to undeploy.</span></span> <span data-ttu-id="3fef4-114">右键单击解决方案资源管理器中的引用，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="3fef4-114">Right click the reference in Solution Explorer, and then click **Remove**.</span></span>  
  
3. <span data-ttu-id="3fef4-115">打开 BizTalk 浏览器中，右键单击你想要取消部署，然后单击该程序集**Undeploy**。</span><span class="sxs-lookup"><span data-stu-id="3fef4-115">Open BizTalk Explorer, right-click the assembly that you want to undeploy, and then click **Undeploy**.</span></span>  
  
   <span data-ttu-id="3fef4-116">有关取消部署程序集的详细信息，请参阅"正在取消部署程序集使用 BizTalk 浏览器"中 BizTalk Server 帮助。</span><span class="sxs-lookup"><span data-stu-id="3fef4-116">For more information about undeploying an assembly, see "Undeploying an Assembly Using BizTalk Explorer" in BizTalk Server Help.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fef4-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="3fef4-117">See Also</span></span>  
 [<span data-ttu-id="3fef4-118">为使用批处理教程做准备</span><span class="sxs-lookup"><span data-stu-id="3fef4-118">Preparing to Use the Batching Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-batching-tutorial.md)