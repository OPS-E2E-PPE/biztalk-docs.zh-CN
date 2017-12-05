---
title: "VisualStudioHostRestart （应用程序部署示例） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d0b82627-1552-479d-a083-cdc9fe4843c3
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d98a3a5e497a4476de897c8008f3a9976812209a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="visualstudiohostrestart-application-deployment-sample"></a><span data-ttu-id="bb6c7-102">VisualStudioHostRestart（应用程序部署示例）</span><span class="sxs-lookup"><span data-stu-id="bb6c7-102">VisualStudioHostRestart (Application Deployment Sample)</span></span>
<span data-ttu-id="bb6c7-103">本主题解释如何使用 VisualStudioHostRestart 示例脚本在本地计算机上重新启动在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 下运行的主机实例。</span><span class="sxs-lookup"><span data-stu-id="bb6c7-103">This topic explains how to use the VisualStudioHostRestart sample script to restart a host instance running under [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] on the local computer.</span></span> <span data-ttu-id="bb6c7-104">在 Visual Studio 中重新部署程序集时可以使用该脚本，以便 BizTalk Server 运行时能够立即应用更改。</span><span class="sxs-lookup"><span data-stu-id="bb6c7-104">You can use this script when redeploying assemblies in Visual Studio so that the BizTalk Server runtime immediately picks up the changes.</span></span> <span data-ttu-id="bb6c7-105">另外，可以使用选项以重新启动主机实例，该选项可以在项目的部署属性中进行设置。</span><span class="sxs-lookup"><span data-stu-id="bb6c7-105">Alternatively, you can use the option to restart host instances, which you can set in Deployment properties for the project.</span></span> <span data-ttu-id="bb6c7-106">有关详细信息，请参阅[如何在 Visual Studio 中设置部署属性](../core/how-to-set-deployment-properties-in-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="bb6c7-106">For more information, see [How to Set Deployment Properties in Visual Studio](../core/how-to-set-deployment-properties-in-visual-studio.md).</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="bb6c7-107">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="bb6c7-107">What This Sample Does</span></span>  
 <span data-ttu-id="bb6c7-108">本示例脚本按顺序执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="bb6c7-108">This sample script performs the following actions, in order:</span></span>  
  
1.  <span data-ttu-id="bb6c7-109">停止本地计算机上的所有进程内主机实例。</span><span class="sxs-lookup"><span data-stu-id="bb6c7-109">Stops all in-process host instances on the local computer.</span></span>  
  
2.  <span data-ttu-id="bb6c7-110">启动本地计算机上的所有进程内主机实例。</span><span class="sxs-lookup"><span data-stu-id="bb6c7-110">Starts all in-process host instances on the local computer.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="bb6c7-111">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="bb6c7-111">Where to Find This Sample</span></span>  
 <span data-ttu-id="bb6c7-112">示例位于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装文件夹，，如下所示： *\<示例路径\>*\Application Deployment\VisualStudioHostRestart。</span><span class="sxs-lookup"><span data-stu-id="bb6c7-112">The sample is located in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation folder, as follows: *\<Samples path\>*\Application Deployment\VisualStudioHostRestart.</span></span>  
  
 <span data-ttu-id="bb6c7-113">示例包括以下文件：</span><span class="sxs-lookup"><span data-stu-id="bb6c7-113">The sample includes the following file:</span></span>  
  
-   <span data-ttu-id="bb6c7-114">RestartBizTalkHostInstances.vbs</span><span class="sxs-lookup"><span data-stu-id="bb6c7-114">RestartBizTalkHostInstances.vbs</span></span>  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="bb6c7-115">如何使用本示例</span><span class="sxs-lookup"><span data-stu-id="bb6c7-115">How to Use This Sample</span></span>  
 <span data-ttu-id="bb6c7-116">请使用以下过程运行本示例。</span><span class="sxs-lookup"><span data-stu-id="bb6c7-116">Use the following procedures to run this sample.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="bb6c7-117">运行示例</span><span class="sxs-lookup"><span data-stu-id="bb6c7-117">To run the sample</span></span>  
  
-   <span data-ttu-id="bb6c7-118">运行 RestartBizTalkHostInstances.vbs。</span><span class="sxs-lookup"><span data-stu-id="bb6c7-118">Run RestartBizTalkHostInstances.vbs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb6c7-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bb6c7-119">See Also</span></span>  
 <span data-ttu-id="bb6c7-120">[应用程序部署 （BizTalk Server 示例文件夹中）](../core/application-deployment-biztalk-server-samples-folder.md) </span><span class="sxs-lookup"><span data-stu-id="bb6c7-120">[Application Deployment (BizTalk Server Samples Folder)](../core/application-deployment-biztalk-server-samples-folder.md) </span></span>  
 <span data-ttu-id="bb6c7-121">[部署到 BizTalk 应用程序从 Visual Studio BizTalk 程序集](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md) </span><span class="sxs-lookup"><span data-stu-id="bb6c7-121">[Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md) </span></span>  
 [<span data-ttu-id="bb6c7-122">部署 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="bb6c7-122">Deploying BizTalk Applications</span></span>](../core/deploying-biztalk-applications.md)