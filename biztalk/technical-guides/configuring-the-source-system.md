---
title: 配置源系统 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 722dd52c-1eea-453c-9a36-9b8d9cf19350
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 73f5d785c20d1390ae811d737e9169951e0270e7
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009302"
---
# <a name="configuring-the-source-system"></a><span data-ttu-id="00b1d-102">配置源系统</span><span class="sxs-lookup"><span data-stu-id="00b1d-102">Configuring the Source System</span></span>
<span data-ttu-id="00b1d-103">对于 BizTalk Server 日志传送，它并不重要如果源系统位于单个[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例或如果它在 Windows Server 群集中承载的多个实例之间分布。</span><span class="sxs-lookup"><span data-stu-id="00b1d-103">For the purposes of BizTalk Server log shipping, it does not matter if the source system is located on a single [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance or if it is distributed among multiple instances hosted in a Windows Server cluster.</span></span> <span data-ttu-id="00b1d-104">没有成功运行 BizTalk Server 中备份作业所需的之外的其他注意事项。</span><span class="sxs-lookup"><span data-stu-id="00b1d-104">There are no additional considerations other than those required to successfully run the Backup BizTalk Server job.</span></span> <span data-ttu-id="00b1d-105">若要配置此作业，请参阅[如何配置备份 BizTalk Server 作业](http://go.microsoft.com/fwlink/?LinkID=154072)(http://go.microsoft.com/fwlink/?LinkID=154072) BizTalk Server 帮助中。</span><span class="sxs-lookup"><span data-stu-id="00b1d-105">To configure this job, see [How to Configure the Backup BizTalk Server Job](http://go.microsoft.com/fwlink/?LinkID=154072) (http://go.microsoft.com/fwlink/?LinkID=154072) in BizTalk Server Help.</span></span> <span data-ttu-id="00b1d-106">你已配置备份 BizTalk Server 作业后，请转到主题[如何配置目标系统](../technical-guides/how-to-configure-the-destination-system.md)。</span><span class="sxs-lookup"><span data-stu-id="00b1d-106">After you have configured the Backup BizTalk Server Job, proceed to the topic [How to Configure the Destination System](../technical-guides/how-to-configure-the-destination-system.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00b1d-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="00b1d-107">See Also</span></span>  
 [<span data-ttu-id="00b1d-108">配置 BizTalk Server 日志传送</span><span class="sxs-lookup"><span data-stu-id="00b1d-108">Configuring BizTalk Server Log Shipping</span></span>](../technical-guides/configuring-biztalk-server-log-shipping.md)