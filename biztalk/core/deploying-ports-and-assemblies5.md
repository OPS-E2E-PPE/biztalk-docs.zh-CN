---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-peoplesoft-enterprise/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: ed7dd37633fc308cccedf40b321f46bf4c2b8ea2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972062"
---
# <a name="deploying-ports-and-assemblies"></a><span data-ttu-id="f6590-101">部署端口和程序集</span><span class="sxs-lookup"><span data-stu-id="f6590-101">Deploying Ports and Assemblies</span></span>
<span data-ttu-id="f6590-102">使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，可在目标计算机上复制端口和程序集。</span><span class="sxs-lookup"><span data-stu-id="f6590-102">Using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can duplicate ports and assemblies on a target computer.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="f6590-103"> 导出的发送端口/接收位置配置为 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="f6590-103"> exports the send ports/receive location configuration into an XML file.</span></span>  
  
 <span data-ttu-id="f6590-104">您可使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 执行下列任务：</span><span class="sxs-lookup"><span data-stu-id="f6590-104">You use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to perform these tasks:</span></span>  
  
- <span data-ttu-id="f6590-105">将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 程序集部署到 BizTalk 配置数据库中或从其中删除。</span><span class="sxs-lookup"><span data-stu-id="f6590-105">Deploy or remove [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] assemblies in a BizTalk Configuration database.</span></span>  
  
- <span data-ttu-id="f6590-106">将程序集安装在全局程序集缓存 (GAC) 中或从其卸载。</span><span class="sxs-lookup"><span data-stu-id="f6590-106">Install or uninstall the assemblies in the global assembly cache (GAC).</span></span>  
  
- <span data-ttu-id="f6590-107">将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 程序集绑定信息导入到绑定文件或从其中导出。</span><span class="sxs-lookup"><span data-stu-id="f6590-107">Import or export [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] assembly binding information to and from binding files.</span></span>  
  
  <span data-ttu-id="f6590-108">有关如何使用信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]若要部署端口和程序集，请参阅[如何导出 BizTalk 应用程序的绑定](../core/how-to-export-bindings-for-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="f6590-108">For information about how to use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to deploy ports and assemblies, see [How to Export Bindings for a BizTalk Application](../core/how-to-export-bindings-for-a-biztalk-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f6590-109">用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器只要求在源 （开发） 计算机上具有 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="f6590-109">The Microsoft BizTalk Adapter for PeopleSoft Enterprise only requires that you have Visual Studio on a source (development) computer.</span></span> <span data-ttu-id="f6590-110">在生产计算机上不要求使用 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="f6590-110">Visual Studio is not required on the production computer.</span></span>  
  
