---
title: "第 8 课： 构建和部署程序集 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- building assemblies
- deploying, assemblies
- assemblies, building
- assemblies, deploying
ms.assetid: 74c9dfbd-8365-4600-8885-a9d9c3490dd5
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 607b3a304260e67a6640e579924705719ff8b850
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="lesson-8-building-and-deploying-the-assembly"></a><span data-ttu-id="7dd23-102">第 8 课： 构建和部署程序集</span><span class="sxs-lookup"><span data-stu-id="7dd23-102">Lesson 8: Building and Deploying the Assembly</span></span>
<span data-ttu-id="7dd23-103">在本课程中，你可以生成和部署管道项目生成包含你在前面的步骤中创建管道的程序集。</span><span class="sxs-lookup"><span data-stu-id="7dd23-103">In this lesson, you build and deploy the pipeline project to generate an assembly that contains the pipelines you created in the previous steps.</span></span> <span data-ttu-id="7dd23-104">本课程可确保到目前为止创建的工作中没有任何编译错误。</span><span class="sxs-lookup"><span data-stu-id="7dd23-104">This lesson ensures there are no compilation errors in the work you have created so far.</span></span>  
  
 <span data-ttu-id="7dd23-105">将项目编译为程序集 (DLL) 文件并将其保存在\<*驱动器*\>: files\microsoft BizTalk Accelerator for SWIFT\bin\Development 文件夹。</span><span class="sxs-lookup"><span data-stu-id="7dd23-105">You compile the project into an assembly (DLL) file and save it in the \<*drive*\>:\Program Files\Microsoft BizTalk Accelerator for SWIFT\bin\Development folder.</span></span>  
  
### <a name="to-build-and-deploy-the-project"></a><span data-ttu-id="7dd23-106">生成并部署项目</span><span class="sxs-lookup"><span data-stu-id="7dd23-106">To build and deploy the project</span></span>  
  
1.  <span data-ttu-id="7dd23-107">在解决方案资源管理器，右键单击**SWIFTPipelines**，然后单击**生成**。</span><span class="sxs-lookup"><span data-stu-id="7dd23-107">In Solution Explorer, right-click **SWIFTPipelines**, and then click **Build**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7dd23-108">在编译过程中，不应看到任何失败。</span><span class="sxs-lookup"><span data-stu-id="7dd23-108">During the compilation process, you should not see any failures.</span></span> <span data-ttu-id="7dd23-109">如果这样做，请检查错误的源，其更正，然后重新生成项目。</span><span class="sxs-lookup"><span data-stu-id="7dd23-109">If you do, check the source of the error, correct it and then re-build the project.</span></span> <span data-ttu-id="7dd23-110">但是，可能会看到大量的 A4SWIFT 管道组件相关的警告。</span><span class="sxs-lookup"><span data-stu-id="7dd23-110">You may, however, see a number of warnings related to the A4SWIFT pipeline components.</span></span> <span data-ttu-id="7dd23-111">您可以更正导致通过设置这些警告的条件**Copy Local**的管道组件引用的属性**False**。</span><span class="sxs-lookup"><span data-stu-id="7dd23-111">You can correct the condition leading to these warnings by setting the **Copy Local** properties of the pipeline component references to **False**.</span></span> <span data-ttu-id="7dd23-112">有关详细信息，请参阅"生成管道项目可能会导致警告"[杂项已知问题](http://msdn.microsoft.com/library/bc94c781-2a56-4f80-8ecb-e654de2f6ed6)。</span><span class="sxs-lookup"><span data-stu-id="7dd23-112">For more information, see "Building a pipeline project may result in warnings" in [Miscellaneous Known Issues](http://msdn.microsoft.com/library/bc94c781-2a56-4f80-8ecb-e654de2f6ed6).</span></span>  
  
2.  <span data-ttu-id="7dd23-113">若要验证的 SWIFTPipelines.dll 创建文件，请使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器，浏览到\<*驱动器*:\>\labs\SWIFTProject\SWIFTPipelines\bin\Development，并确保该文件中存在此文件夹中。</span><span class="sxs-lookup"><span data-stu-id="7dd23-113">To verify the creation of the SWIFTPipelines.dll file, using [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, browse to \<*drive*:\>\labs\SWIFTProject\SWIFTPipelines\bin\Development, and ensure that the file exists in this folder.</span></span>  
  
3.  <span data-ttu-id="7dd23-114">在解决方案资源管理器，右键单击**SWIFTPipelines**，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="7dd23-114">In Solution Explorer, right-click **SWIFTPipelines**, and then click **Deploy**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7dd23-115">在部署过程中，你不应看到任何失败或警告。</span><span class="sxs-lookup"><span data-stu-id="7dd23-115">During the deployment process, you should not see any failures or warnings.</span></span> <span data-ttu-id="7dd23-116">如果这样做，请检查错误的源、 其更正，然后重新部署该项目。</span><span class="sxs-lookup"><span data-stu-id="7dd23-116">If you do, check the source of the error, correct it, and then re-deploy the project.</span></span>  
  
4.  <span data-ttu-id="7dd23-117">若要在符合部署成功，**视图**菜单[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，单击**BizTalk 资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="7dd23-117">To conform deployment success, in the **View** menu of [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], click **BizTalk Explorer**.</span></span>  
  
5.  <span data-ttu-id="7dd23-118">右键单击**BizTalk 配置数据库**，然后单击**刷新**。</span><span class="sxs-lookup"><span data-stu-id="7dd23-118">Right-click **BizTalk Configuration Databases**, and then click **Refresh**.</span></span>  
  
6.  <span data-ttu-id="7dd23-119">展开**程序集**节点并确认快捷键成功部署**SWIFTPipelines (1.0.0.0)**。</span><span class="sxs-lookup"><span data-stu-id="7dd23-119">Expand the **Assemblies** node and confirm that the accelerator successfully deployed **SWIFTPipelines (1.0.0.0)**.</span></span>  
  
 <span data-ttu-id="7dd23-120">继续执行[模块 4： 创建 XML 接收和平面文件发送端口](../../adapters-and-accelerators/accelerator-swift/module-4-adding-an-xml-receive-location-and-flat-file-send-port.md)。</span><span class="sxs-lookup"><span data-stu-id="7dd23-120">Proceed to [Module 4: Creating XML Receive and Flat File Send Ports](../../adapters-and-accelerators/accelerator-swift/module-4-adding-an-xml-receive-location-and-flat-file-send-port.md).</span></span>