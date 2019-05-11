---
title: BizTalk Server 迁移疑难解答 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e6eddc0a-2403-4bcd-9327-23f51ce7d57b
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 931dd72f3c6ffc73209fca61a1c75becd30151c7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398680"
---
# <a name="troubleshooting-biztalk-server-migration"></a><span data-ttu-id="cdd33-102">BizTalk Server 迁移疑难解答</span><span class="sxs-lookup"><span data-stu-id="cdd33-102">Troubleshooting BizTalk Server Migration</span></span>
<span data-ttu-id="cdd33-103">本部分提供有关从应用程序迁移 BizTalk 时遇到的常见问题的信息的一个集中的位置[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]2009 升级到 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="cdd33-103">This section provides a centralized location for information about common problems encountered while migrating BizTalk applications from [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2009 to BizTalk Server.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="cdd33-104">已知问题</span><span class="sxs-lookup"><span data-stu-id="cdd33-104">Known Issues</span></span>  
  
#### <a name="custom-applications-might-not-work-while-upgrading"></a><span data-ttu-id="cdd33-105">自定义应用程序可能无法工作时升级</span><span class="sxs-lookup"><span data-stu-id="cdd33-105">Custom applications might not work while upgrading</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="cdd33-106">问题</span><span class="sxs-lookup"><span data-stu-id="cdd33-106">Problem</span></span>  
 <span data-ttu-id="cdd33-107">从升级时[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]2009 升级到 BizTalk Server 中，某些自定义应用程序可能无法工作。</span><span class="sxs-lookup"><span data-stu-id="cdd33-107">While upgrading from [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2009 to BizTalk Server, some custom applications might not work.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="cdd33-108">原因</span><span class="sxs-lookup"><span data-stu-id="cdd33-108">Cause</span></span>  
 <span data-ttu-id="cdd33-109">所有 BizTalk 都托管代码组件在 CLR 4.0 上运行。</span><span class="sxs-lookup"><span data-stu-id="cdd33-109">All the BizTalk managed code components run on CLR 4.0.</span></span> <span data-ttu-id="cdd33-110">这些组件编译针对[!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)]，他们需要一个配置文件用于在 CLR 4.0 上运行。</span><span class="sxs-lookup"><span data-stu-id="cdd33-110">As these components are compiled against [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)], they need a config file to run in CLR 4.0.</span></span>  
  
##### <a name="solution"></a><span data-ttu-id="cdd33-111">解决方案</span><span class="sxs-lookup"><span data-stu-id="cdd33-111">Solution</span></span>  
 <span data-ttu-id="cdd33-112">若要解决此问题，请更新配置文件。</span><span class="sxs-lookup"><span data-stu-id="cdd33-112">To resolve this issue, update the config file.</span></span>  
  
```  
<configuration>  
<startup useLegacyV2RuntimeActivationPolicy="true">  
<supportedRuntime version="v4.0" />  
</startup>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cdd33-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="cdd33-113">See Also</span></span>  
 [<span data-ttu-id="cdd33-114">故障排除</span><span class="sxs-lookup"><span data-stu-id="cdd33-114">Troubleshooting</span></span>](../core/troubleshooting.md)