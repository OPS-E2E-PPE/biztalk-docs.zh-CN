---
title: "更新某个项目 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 40feab57-4286-4bdf-8f52-25d02b3fa60c
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17d5f2ad910c59ded9c2499c929d73480fac7b51
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="updating-an-artifact"></a><span data-ttu-id="4447c-102">更新某个项目</span><span class="sxs-lookup"><span data-stu-id="4447c-102">Updating an Artifact</span></span>
<span data-ttu-id="4447c-103">在两个或多个 BizTalk 应用程序中的项目之间的依赖关系可以显著影响应用程序部署和维护。</span><span class="sxs-lookup"><span data-stu-id="4447c-103">Dependencies between artifacts in two or more BizTalk applications can have a significant effect on application deployment and maintenance.</span></span> <span data-ttu-id="4447c-104">它需要使用该项目才能正常运行时依赖于另一个项目，例如业务流程，需要使用特定的管道，以正确传输消息。</span><span class="sxs-lookup"><span data-stu-id="4447c-104">An artifact is dependent on another when it needs to use that artifact in order to function properly, for example an orchestration that needs to use a specific pipeline in order to transmit messages correctly.</span></span>  
  
 <span data-ttu-id="4447c-105">若要更新应用程序中的项目，必须首先取消它，部署以及任何依赖于它的项目中。</span><span class="sxs-lookup"><span data-stu-id="4447c-105">To update an artifact in an application, you must first undeploy it, along with any artifacts that depend on it.</span></span> <span data-ttu-id="4447c-106">在具有依存关系的多个项目存在于同一应用程序中时，BizTalk Server 自动处理更新的和依赖的项目的取消部署和重新部署任务。</span><span class="sxs-lookup"><span data-stu-id="4447c-106">When artifacts that have dependencies exist in the same application, BizTalk Server automatically handles the undeployment and redeployment tasks for the updated and dependent artifacts.</span></span> <span data-ttu-id="4447c-107">但在具有依存关系的项目存在于不同应用程序时，就无法自动完成上述任务了。</span><span class="sxs-lookup"><span data-stu-id="4447c-107">When artifacts that have dependencies exist in different applications, however, this is not the case.</span></span> <span data-ttu-id="4447c-108">如果你想要更新的应用程序中，项目和其他应用程序中的项目具有的依赖关系，你必须取消部署并，如下所示手动重新部署依赖项目：</span><span class="sxs-lookup"><span data-stu-id="4447c-108">If you want to update an artifact in one application, and an artifact in another application has a dependency on it, you must undeploy and redeploy the dependent artifact manually as follows:</span></span>  
  
1.  <span data-ttu-id="4447c-109">停止、取消登记和取消绑定依赖的程序集。</span><span class="sxs-lookup"><span data-stu-id="4447c-109">Stop, unenlist, and unbind the dependent artifact.</span></span>  
  
2.  <span data-ttu-id="4447c-110">更新它依赖的程序集。</span><span class="sxs-lookup"><span data-stu-id="4447c-110">Update the artifact on which it depends.</span></span>  
  
3.  <span data-ttu-id="4447c-111">绑定、登记和启动依赖的程序集。</span><span class="sxs-lookup"><span data-stu-id="4447c-111">Bind, enlist, and start the dependent artifact.</span></span>  
  
 <span data-ttu-id="4447c-112">若要避免需要执行手动步骤来更新上的项目的其他项目依赖，你可以尝试将具有依赖项的所有项目都放在同一个应用程序。</span><span class="sxs-lookup"><span data-stu-id="4447c-112">To avoid the need to perform manual steps to update an artifact on which other artifacts depend, you can try to keep all artifacts with dependencies together in the same application.</span></span> <span data-ttu-id="4447c-113">这并不总是有可能，但是，由于大多数类型的项目必须是唯一 BizTalk 组中。</span><span class="sxs-lookup"><span data-stu-id="4447c-113">This is not always possible, however, because most types of artifacts must be unique in a BizTalk group.</span></span> <span data-ttu-id="4447c-114">您不能在同一组的两个不同应用程序中具有相同的项目，即使这两个应用程序都包含依赖于相同项目的项目。</span><span class="sxs-lookup"><span data-stu-id="4447c-114">You cannot have the same artifact in two different applications in the same group, even if both applications contain artifacts that depend on the same artifact.</span></span> <span data-ttu-id="4447c-115">有关问题的唯一项目的详细信息，请参阅[项目，必须是唯一的应用程序或组](http://go.microsoft.com/fwlink/?LinkId=155141)(http://go.microsoft.com/fwlink/?LinkId=155141) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="4447c-115">For more information about the issue of unique artifacts, see [Artifacts That Must Be Unique in an Application or Group](http://go.microsoft.com/fwlink/?LinkId=155141) (http://go.microsoft.com/fwlink/?LinkId=155141) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
 <span data-ttu-id="4447c-116">你可以将所需的项目添加到一个应用程序，然后添加对该应用程序中包含依赖于它的项目的任何其他应用程序的引用。</span><span class="sxs-lookup"><span data-stu-id="4447c-116">You can add the needed artifact to one application and then add a reference to that application from any other applications containing artifacts that depend on it.</span></span> <span data-ttu-id="4447c-117">在您添加对某一应用程序的引用时，该应用程序中的项目可以使用它引用的应用程序中的任何项目。</span><span class="sxs-lookup"><span data-stu-id="4447c-117">When you add a reference to an application, artifacts in the application can use any artifacts in the application that it references.</span></span> <span data-ttu-id="4447c-118">有关添加引用的说明，请参阅[如何添加对另一个应用程序的引用](http://go.microsoft.com/fwlink/?LinkID=155011)(http://go.microsoft.com/fwlink/?LinkID=155011) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="4447c-118">For instructions on adding a reference, see [How to Add a Reference to Another Application](http://go.microsoft.com/fwlink/?LinkID=155011) (http://go.microsoft.com/fwlink/?LinkID=155011) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
 <span data-ttu-id="4447c-119">用于更新 BizTalk 应用程序中的项目的任务的清单，请参阅[清单： 更新 BizTalk 应用程序中的项目](http://go.microsoft.com/fwlink/?LinkId=155647)(http://go.microsoft.com/fwlink/?LinkId=155647) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="4447c-119">For a checklist of tasks for updating artifacts in a BizTalk application, see [Checklist: Update the Artifacts in a BizTalk Application](http://go.microsoft.com/fwlink/?LinkId=155647) (http://go.microsoft.com/fwlink/?LinkId=155647) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4447c-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4447c-120">See Also</span></span>  
 [<span data-ttu-id="4447c-121">更新应用程序和项目</span><span class="sxs-lookup"><span data-stu-id="4447c-121">Updating Applications and Artifacts</span></span>](../technical-guides/updating-applications-and-artifacts.md)