---
title: VisualStudioHostRestart （应用程序部署示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d0b82627-1552-479d-a083-cdc9fe4843c3
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96cc470bde0ca8b62a25de81a272d2cf8a891971
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65320827"
---
# <a name="visualstudiohostrestart-application-deployment-sample"></a><span data-ttu-id="fd2df-102">VisualStudioHostRestart （应用程序部署示例）</span><span class="sxs-lookup"><span data-stu-id="fd2df-102">VisualStudioHostRestart (Application Deployment Sample)</span></span>
<span data-ttu-id="fd2df-103">本主题说明如何使用 VisualStudioHostRestart 示例脚本来重新启动主机实例下运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]本地计算机上。</span><span class="sxs-lookup"><span data-stu-id="fd2df-103">This topic explains how to use the VisualStudioHostRestart sample script to restart a host instance running under [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] on the local computer.</span></span> <span data-ttu-id="fd2df-104">重新部署 Visual Studio 中的程序集，以便 BizTalk Server 运行时立即提取所做的更改时，可以使用此脚本。</span><span class="sxs-lookup"><span data-stu-id="fd2df-104">You can use this script when redeploying assemblies in Visual Studio so that the BizTalk Server runtime immediately picks up the changes.</span></span> <span data-ttu-id="fd2df-105">或者，可以使用该选项以重新启动主机实例，您可以在项目的部署属性中设置。</span><span class="sxs-lookup"><span data-stu-id="fd2df-105">Alternatively, you can use the option to restart host instances, which you can set in Deployment properties for the project.</span></span> <span data-ttu-id="fd2df-106">有关详细信息，请参阅[如何在 Visual Studio 中设置部署属性](../core/how-to-set-deployment-properties-in-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="fd2df-106">For more information, see [How to Set Deployment Properties in Visual Studio](../core/how-to-set-deployment-properties-in-visual-studio.md).</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="fd2df-107">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="fd2df-107">What This Sample Does</span></span>  
 <span data-ttu-id="fd2df-108">此示例脚本按顺序执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="fd2df-108">This sample script performs the following actions, in order:</span></span>  
  
1.  <span data-ttu-id="fd2df-109">在本地计算机上停止所有进程内主机实例。</span><span class="sxs-lookup"><span data-stu-id="fd2df-109">Stops all in-process host instances on the local computer.</span></span>  
  
2.  <span data-ttu-id="fd2df-110">在本地计算机上启动所有进程内主机实例。</span><span class="sxs-lookup"><span data-stu-id="fd2df-110">Starts all in-process host instances on the local computer.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="fd2df-111">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="fd2df-111">Where to Find This Sample</span></span>  
 <span data-ttu-id="fd2df-112">该示例位于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装文件夹中的，按如下所示：*\<示例路径\>* \Application Deployment\VisualStudioHostRestart。</span><span class="sxs-lookup"><span data-stu-id="fd2df-112">The sample is located in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation folder, as follows: *\<Samples path\>* \Application Deployment\VisualStudioHostRestart.</span></span>  
  
 <span data-ttu-id="fd2df-113">示例包括以下文件：</span><span class="sxs-lookup"><span data-stu-id="fd2df-113">The sample includes the following file:</span></span>  
  
-   <span data-ttu-id="fd2df-114">RestartBizTalkHostInstances.vbs</span><span class="sxs-lookup"><span data-stu-id="fd2df-114">RestartBizTalkHostInstances.vbs</span></span>  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="fd2df-115">如何使用此示例</span><span class="sxs-lookup"><span data-stu-id="fd2df-115">How to Use This Sample</span></span>  
 <span data-ttu-id="fd2df-116">使用以下过程才能运行此示例。</span><span class="sxs-lookup"><span data-stu-id="fd2df-116">Use the following procedures to run this sample.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="fd2df-117">若要运行示例</span><span class="sxs-lookup"><span data-stu-id="fd2df-117">To run the sample</span></span>  
  
-   <span data-ttu-id="fd2df-118">运行 RestartBizTalkHostInstances.vbs。</span><span class="sxs-lookup"><span data-stu-id="fd2df-118">Run RestartBizTalkHostInstances.vbs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd2df-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="fd2df-119">See Also</span></span>  
 <span data-ttu-id="fd2df-120">[应用程序部署 （BizTalk Server 示例文件夹）](../core/application-deployment-biztalk-server-samples-folder.md) </span><span class="sxs-lookup"><span data-stu-id="fd2df-120">[Application Deployment (BizTalk Server Samples Folder)](../core/application-deployment-biztalk-server-samples-folder.md) </span></span>  
 <span data-ttu-id="fd2df-121">[部署 BizTalk 程序集从 Visual Studio 到 BizTalk 应用程序](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md) </span><span class="sxs-lookup"><span data-stu-id="fd2df-121">[Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md) </span></span>  
 [<span data-ttu-id="fd2df-122">部署 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="fd2df-122">Deploying BizTalk Applications</span></span>](../core/deploying-biztalk-applications.md)