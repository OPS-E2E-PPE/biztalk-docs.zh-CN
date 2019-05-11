---
title: 配置 BizTalk 日志传送的其他数据库 |Microsoft Docs
description: 将自定义数据库添加到备份 BizTalk Server 作业和 BizTalk Server 中的日志传送
ms.custom: ''
ms.date: 11/01/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2fc2ae67-5cb9-4d53-9bf7-c88f84914960
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b44031464846dbaab484a9eb29e672371778ddae
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244070"
---
# <a name="configuring-biztalk-server-log-shipping-for-additional-databases"></a><span data-ttu-id="65869-103">配置 BizTalk Server 日志传送的其他数据库</span><span class="sxs-lookup"><span data-stu-id="65869-103">Configuring BizTalk Server Log Shipping for Additional Databases</span></span>

## <a name="overview"></a><span data-ttu-id="65869-104">概述</span><span class="sxs-lookup"><span data-stu-id="65869-104">Overview</span></span>
<span data-ttu-id="65869-105">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，添加到备份 BizTalk Server 作业的作业会自动添加到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]日志传送。</span><span class="sxs-lookup"><span data-stu-id="65869-105">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], jobs added to the Backup BizTalk Server job are automatically added to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping.</span></span> <span data-ttu-id="65869-106">不需要采取其他步骤来配置新的数据库添加到备份 BizTalk Server 作业的日志传送。</span><span class="sxs-lookup"><span data-stu-id="65869-106">You do not have to take additional steps to configure log shipping for new databases added to the Backup BizTalk Server job.</span></span> <span data-ttu-id="65869-107">但是，请确保将自定义数据库添加为在相应\<OtherDatabases\> SampleUpdateInfo.xml 文件部分。</span><span class="sxs-lookup"><span data-stu-id="65869-107">However, be sure to add custom databases as appropriate under the \<OtherDatabases\> section of the SampleUpdateInfo.xml file.</span></span> <span data-ttu-id="65869-108">[为使日志传送配置的目标系统](../core/how-to-configure-the-destination-system-for-log-shipping.md)并[返回自定义数据库](../core/how-to-back-up-custom-databases.md)提供一些指导。</span><span class="sxs-lookup"><span data-stu-id="65869-108">[Configure the Destination System for Log Shipping](../core/how-to-configure-the-destination-system-for-log-shipping.md) and [Back Up Custom Databases](../core/how-to-back-up-custom-databases.md) provides some guidance.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="65869-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="65869-109">See Also</span></span>  
 [<span data-ttu-id="65869-110">配置 BizTalk Server 日志传送</span><span class="sxs-lookup"><span data-stu-id="65869-110">Configuring BizTalk Server Log Shipping</span></span>](../technical-guides/configuring-biztalk-server-log-shipping.md)