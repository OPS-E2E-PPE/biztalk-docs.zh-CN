---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-jd-edwards-oneworld/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 327ab6150e5b1483e516a351d885c49442a6ed90
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389567"
---
# <a name="deploying-ports-and-assemblies"></a><span data-ttu-id="4b1df-101">部署端口和程序集</span><span class="sxs-lookup"><span data-stu-id="4b1df-101">Deploying Ports and Assemblies</span></span>
<span data-ttu-id="4b1df-102">使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，可以复制端口和目标计算机上的程序集。</span><span class="sxs-lookup"><span data-stu-id="4b1df-102">Using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can duplicate ports and assemblies on a target computer.</span></span> <span data-ttu-id="4b1df-103">BizTalk Server 发送端口/接收位置将配置导出到 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="4b1df-103">BizTalk Server exports the send ports/receive location configuration into an XML file.</span></span>  
  
 <span data-ttu-id="4b1df-104">BizTalk Server 可用于执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="4b1df-104">You can use BizTalk Server to do the following tasks:</span></span>  
  
-   <span data-ttu-id="4b1df-105">部署或 BizTalk 配置数据库中删除 BizTalk Server 程序集</span><span class="sxs-lookup"><span data-stu-id="4b1df-105">Deploy or remove BizTalk Server assemblies in a BizTalk Configuration database</span></span>  
  
-   <span data-ttu-id="4b1df-106">安装或卸载的全局程序集缓存 (GAC) 中的程序集</span><span class="sxs-lookup"><span data-stu-id="4b1df-106">Install or uninstall the assemblies in the global assembly cache (GAC)</span></span>  
  
-   <span data-ttu-id="4b1df-107">导入或导出 BizTalk Server 程序集绑定信息与绑定文件</span><span class="sxs-lookup"><span data-stu-id="4b1df-107">Import or export BizTalk Server assembly binding information to and from binding files</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4b1df-108">用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器只要求在源 （开发） 计算机上具有 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="4b1df-108">The Microsoft BizTalk Adapter for JD Edwards OneWorld only requires that you have Visual Studio on a source (development) computer.</span></span> <span data-ttu-id="4b1df-109">Visual Studio 不需要在生产计算机上。</span><span class="sxs-lookup"><span data-stu-id="4b1df-109">Visual Studio is not required on the production computer.</span></span>  
  
