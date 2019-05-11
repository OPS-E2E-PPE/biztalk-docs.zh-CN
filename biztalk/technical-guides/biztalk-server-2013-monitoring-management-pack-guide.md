---
title: BizTalk Server 2013 监视管理包指南 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d54d4ace-0da6-454f-8311-9fe9471540b4
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e7f85c6ecb05caf0f7e867e4f0ca381d61838f3e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400491"
---
# <a name="biztalk-server-2013-monitoring-management-pack-guide"></a><span data-ttu-id="ac7f1-102">BizTalk Server 2013 监视管理包指南</span><span class="sxs-lookup"><span data-stu-id="ac7f1-102">BizTalk Server 2013 Monitoring Management Pack Guide</span></span>
## <a name="document-version"></a><span data-ttu-id="ac7f1-103">文档版本</span><span class="sxs-lookup"><span data-stu-id="ac7f1-103">Document Version</span></span>  
 <span data-ttu-id="ac7f1-104">本指南编写基于 7.0.389.0 版本[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]2013年管理包。</span><span class="sxs-lookup"><span data-stu-id="ac7f1-104">This guide was written based on the 7.0.389.0 version of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013 Management Pack.</span></span>  
  
### <a name="revision-history"></a><span data-ttu-id="ac7f1-105">修订版本历史记录</span><span class="sxs-lookup"><span data-stu-id="ac7f1-105">Revision History</span></span>  
  
|<span data-ttu-id="ac7f1-106">发布日期</span><span class="sxs-lookup"><span data-stu-id="ac7f1-106">Release Date</span></span>|<span data-ttu-id="ac7f1-107">更改</span><span class="sxs-lookup"><span data-stu-id="ac7f1-107">Changes</span></span>|  
|------------------|-------------|  
|<span data-ttu-id="ac7f1-108">2013 年 7 月</span><span class="sxs-lookup"><span data-stu-id="ac7f1-108">July 2013</span></span>|<span data-ttu-id="ac7f1-109">本文档的原始版本。</span><span class="sxs-lookup"><span data-stu-id="ac7f1-109">Original release of this document.</span></span>|  
|<span data-ttu-id="ac7f1-110">2013 年 10 月</span><span class="sxs-lookup"><span data-stu-id="ac7f1-110">October 2013</span></span>|<span data-ttu-id="ac7f1-111">附录一节中的更新的脚本文本。</span><span class="sxs-lookup"><span data-stu-id="ac7f1-111">Updated script text in the Appendix section.</span></span>|  
|<span data-ttu-id="ac7f1-112">2014 年 7 月</span><span class="sxs-lookup"><span data-stu-id="ac7f1-112">July 2014</span></span>|<span data-ttu-id="ac7f1-113">添加了从 SQL 到"监视"部分中的 SysAdmin 角色要求。</span><span class="sxs-lookup"><span data-stu-id="ac7f1-113">Added SQL to SysAdmin role requirement in “Monitoring” section.</span></span><br /><br /> <span data-ttu-id="ac7f1-114">已更新的管理包下载链接。</span><span class="sxs-lookup"><span data-stu-id="ac7f1-114">Updated MP download link.</span></span>|