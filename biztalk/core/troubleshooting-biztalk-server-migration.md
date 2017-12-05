---
title: "BizTalk Server 迁移的疑难解答 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e6eddc0a-2403-4bcd-9327-23f51ce7d57b
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ddb6d9780a86183de5a09791de44adda5d57dab
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="troubleshooting-biztalk-server-migration"></a><span data-ttu-id="75d65-102">BizTalk Server 迁移疑难解答</span><span class="sxs-lookup"><span data-stu-id="75d65-102">Troubleshooting BizTalk Server Migration</span></span>
<span data-ttu-id="75d65-103">本部分提供有关从迁移 BizTalk 应用程序时遇到的常见问题的信息的一个集中的位置[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]给 BizTalk Server 2009。</span><span class="sxs-lookup"><span data-stu-id="75d65-103">This section provides a centralized location for information about common problems encountered while migrating BizTalk applications from [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2009 to BizTalk Server.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="75d65-104">已知问题</span><span class="sxs-lookup"><span data-stu-id="75d65-104">Known Issues</span></span>  
  
#### <a name="custom-applications-might-not-work-while-upgrading"></a><span data-ttu-id="75d65-105">自定义应用程序可能无法升级时</span><span class="sxs-lookup"><span data-stu-id="75d65-105">Custom applications might not work while upgrading</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="75d65-106">问题</span><span class="sxs-lookup"><span data-stu-id="75d65-106">Problem</span></span>  
 <span data-ttu-id="75d65-107">从升级时[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]给 BizTalk Server 2009 某些自定义应用程序可能无法工作。</span><span class="sxs-lookup"><span data-stu-id="75d65-107">While upgrading from [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2009 to BizTalk Server, some custom applications might not work.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="75d65-108">原因</span><span class="sxs-lookup"><span data-stu-id="75d65-108">Cause</span></span>  
 <span data-ttu-id="75d65-109">所有 BizTalk 都托管在 CLR 4.0 上运行的代码组件。</span><span class="sxs-lookup"><span data-stu-id="75d65-109">All the BizTalk managed code components run on CLR 4.0.</span></span> <span data-ttu-id="75d65-110">由于这些组件是针对 [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] 而编译的，所以它们需要有 config 文件才能在 CLR 4.0 上运行。</span><span class="sxs-lookup"><span data-stu-id="75d65-110">As these components are compiled against [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)], they need a config file to run in CLR 4.0.</span></span>  
  
##### <a name="solution"></a><span data-ttu-id="75d65-111">解决方案</span><span class="sxs-lookup"><span data-stu-id="75d65-111">Solution</span></span>  
 <span data-ttu-id="75d65-112">若要解决此问题，更新配置文件。</span><span class="sxs-lookup"><span data-stu-id="75d65-112">To resolve this issue, update the config file.</span></span>  
  
```  
<configuration>  
<startup useLegacyV2RuntimeActivationPolicy="true">  
<supportedRuntime version="v4.0" />  
</startup>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="75d65-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="75d65-113">See Also</span></span>  
 [<span data-ttu-id="75d65-114">故障排除</span><span class="sxs-lookup"><span data-stu-id="75d65-114">Troubleshooting</span></span>](../core/troubleshooting.md)