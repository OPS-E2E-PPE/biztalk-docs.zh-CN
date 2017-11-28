---
title: "配置 BizTalk Server 日志传送有关的其他数据库 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2fc2ae67-5cb9-4d53-9bf7-c88f84914960
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b16b1d262b07ecaa62e87456f10bece225b3b34
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-biztalk-server-log-shipping-for-additional-databases"></a><span data-ttu-id="465f3-102">配置 BizTalk Server 日志传送有关的其他数据库</span><span class="sxs-lookup"><span data-stu-id="465f3-102">Configuring BizTalk Server Log Shipping for Additional Databases</span></span>
<span data-ttu-id="465f3-103">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，添加到 BizTalk Server 中备份作业的作业会自动添加到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]日志传送。</span><span class="sxs-lookup"><span data-stu-id="465f3-103">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], jobs added to the Backup BizTalk Server job are automatically added to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping.</span></span> <span data-ttu-id="465f3-104">无需执行其他步骤来配置新的数据库添加到 BizTalk Server 中备份作业的日志传送。</span><span class="sxs-lookup"><span data-stu-id="465f3-104">You do not have to take additional steps to configure log shipping for new databases added to the Backup BizTalk Server job.</span></span> <span data-ttu-id="465f3-105">但是，请务必根据需要在添加自定义数据库\<OtherDatabases> SampleUpdateInfo.xml 文件中的步骤 22 所述的部分[如何为日志传送配置目标系统](http://go.microsoft.com/fwlink/?LinkId=151402)(http://go.microsoft.com/fwlink/?LinkId=151402) 中[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="465f3-105">However, be sure to add custom databases as appropriate under the \<OtherDatabases> section of the SampleUpdateInfo.xml file as described in step 22 of [How to Configure the Destination System for Log Shipping](http://go.microsoft.com/fwlink/?LinkId=151402) (http://go.microsoft.com/fwlink/?LinkId=151402) in [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] Help.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="465f3-106">另请参阅</span><span class="sxs-lookup"><span data-stu-id="465f3-106">See Also</span></span>  
 [<span data-ttu-id="465f3-107">配置 BizTalk Server 日志传送</span><span class="sxs-lookup"><span data-stu-id="465f3-107">Configuring BizTalk Server Log Shipping</span></span>](../technical-guides/configuring-biztalk-server-log-shipping.md)