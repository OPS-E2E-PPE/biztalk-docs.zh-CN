---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-jd-edwards-oneworld/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: ac85aec2f1153d5117c95627e573ec563d58dbc2
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="deploying-ports-and-assemblies"></a><span data-ttu-id="af43a-101">部署端口和程序集</span><span class="sxs-lookup"><span data-stu-id="af43a-101">Deploying Ports and Assemblies</span></span>
<span data-ttu-id="af43a-102">使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，可在目标计算机上复制端口和程序集。</span><span class="sxs-lookup"><span data-stu-id="af43a-102">Using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can duplicate ports and assemblies on a target computer.</span></span> <span data-ttu-id="af43a-103">BizTalk Server 将发送端口/接收位置配置导出到一个 XML 文件中。</span><span class="sxs-lookup"><span data-stu-id="af43a-103">BizTalk Server exports the send ports/receive location configuration into an XML file.</span></span>  
  
 <span data-ttu-id="af43a-104">BizTalk Server 可用于执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="af43a-104">You can use BizTalk Server to do the following tasks:</span></span>  
  
-   <span data-ttu-id="af43a-105">将 BizTalk Server 程序集部署到 BizTalk 配置数据库或从其删除</span><span class="sxs-lookup"><span data-stu-id="af43a-105">Deploy or remove BizTalk Server assemblies in a BizTalk Configuration database</span></span>  
  
-   <span data-ttu-id="af43a-106">将程序集安装在全局程序集缓存 (GAC) 中或从其卸载</span><span class="sxs-lookup"><span data-stu-id="af43a-106">Install or uninstall the assemblies in the global assembly cache (GAC)</span></span>  
  
-   <span data-ttu-id="af43a-107">将 BizTalk Server 程序集绑定信息导入到绑定文件或从其导出</span><span class="sxs-lookup"><span data-stu-id="af43a-107">Import or export BizTalk Server assembly binding information to and from binding files</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="af43a-108">JD Edwards OneWorld 的 Microsoft BizTalk 适配器只要求在源（开发）计算机上具有 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="af43a-108">The Microsoft BizTalk Adapter for JD Edwards OneWorld only requires that you have Visual Studio on a source (development) computer.</span></span> <span data-ttu-id="af43a-109">在生产计算机上不要求使用 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="af43a-109">Visual Studio is not required on the production computer.</span></span>  
  
