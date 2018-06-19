---
title: MQSeries 适配器的 XML 配置文件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, mqsconfigwiz
- configuring [MQSeries adapters], silent configuration
- MQSeries adapters, silent configuration
- configuring [MQSeries adapters], mqsconfigwiz
- mqsconfigwiz [MQSeries adapters]
ms.assetid: 5f19e55c-0f2c-46d7-bb5d-1eb147c296b3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a0356c69b90f0dcfd5fc636b302a97b2de5674b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289765"
---
# <a name="xml-configuration-file-for-the-mqseries-adapter"></a><span data-ttu-id="32a0d-102">MQSeries 适配器的 XML 配置文件</span><span class="sxs-lookup"><span data-stu-id="32a0d-102">XML Configuration File for the MQSeries Adapter</span></span>
<span data-ttu-id="32a0d-103">XML 配置文件读取**mqsconfigwiz**包含用户输入时使用该向导的 Windows 版本的相同信息。</span><span class="sxs-lookup"><span data-stu-id="32a0d-103">The XML configuration file read by **mqsconfigwiz** contains the same information a user enters when using the Windows version of the wizard.</span></span> <span data-ttu-id="32a0d-104">此信息包括应用程序标识以及用户 ID 和密码（如果需要）、角色名称，以及该角色所包含用户的列表。</span><span class="sxs-lookup"><span data-stu-id="32a0d-104">This information includes the application identity and the user ID and password if required, the role name, and a list of users who are part of that role.</span></span>  
  
 <span data-ttu-id="32a0d-105">该文件的示例如下所示：</span><span class="sxs-lookup"><span data-stu-id="32a0d-105">An example of the file might appear as follows:</span></span>  
  
```  
<MQSeriesConfig>  
    <AppIdentity>thisuser</AppIdentity>  
    <userid>domain\username</userid>  
    <password>Bippity.Boppity</password>  
    <rolename>CreatorOwner</rolename>  
    <userlist>  
        <username>domain\user1</username>  
        <username>domain\user2</username>  
    </userlist>  
</MQSeriesConfig>  
```  
  
 <span data-ttu-id="32a0d-106">你可以使用**thisuser**， **InteractiveUser**， **LocalService**，或**NetworkService**一样的值**AppIdentity**.</span><span class="sxs-lookup"><span data-stu-id="32a0d-106">You can use **thisuser**, **InteractiveUser**, **LocalService**, or **NetworkService** as values for **AppIdentity**.</span></span> <span data-ttu-id="32a0d-107">使用**userid**和**密码**仅具有元素**thisuser**。</span><span class="sxs-lookup"><span data-stu-id="32a0d-107">Use the **userid** and **password** elements only with **thisuser**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32a0d-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="32a0d-108">See Also</span></span>  
 [<span data-ttu-id="32a0d-109">无提示 MQSeries 适配器配置</span><span class="sxs-lookup"><span data-stu-id="32a0d-109">Silent Configuration of the MQSeries Adapter</span></span>](../core/silent-configuration-of-the-mqseries-adapter.md)