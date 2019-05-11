---
title: MQSeries 适配器的 XML 配置文件 |Microsoft Docs
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
ms.openlocfilehash: 32ba4c90f082b15c43fd04f8c2de22b31f16bdfd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65295363"
---
# <a name="xml-configuration-file-for-the-mqseries-adapter"></a><span data-ttu-id="1514b-102">MQSeries 适配器的 XML 配置文件</span><span class="sxs-lookup"><span data-stu-id="1514b-102">XML Configuration File for the MQSeries Adapter</span></span>
<span data-ttu-id="1514b-103">读取 XML 配置文件**mqsconfigwiz**包含用户输入时使用 Windows 版本的向导相同的信息。</span><span class="sxs-lookup"><span data-stu-id="1514b-103">The XML configuration file read by **mqsconfigwiz** contains the same information a user enters when using the Windows version of the wizard.</span></span> <span data-ttu-id="1514b-104">此信息包括应用程序标识和用户 ID 和密码，如果需要、 角色名称和属于该角色的用户的列表。</span><span class="sxs-lookup"><span data-stu-id="1514b-104">This information includes the application identity and the user ID and password if required, the role name, and a list of users who are part of that role.</span></span>  
  
 <span data-ttu-id="1514b-105">文件的示例可能如下所示：</span><span class="sxs-lookup"><span data-stu-id="1514b-105">An example of the file might appear as follows:</span></span>  
  
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
  
 <span data-ttu-id="1514b-106">可以使用**thisuser**， **InteractiveUser**， **LocalService**，或者**NetworkService**作为值**AppIdentity**.</span><span class="sxs-lookup"><span data-stu-id="1514b-106">You can use **thisuser**, **InteractiveUser**, **LocalService**, or **NetworkService** as values for **AppIdentity**.</span></span> <span data-ttu-id="1514b-107">使用**userid**并**密码**仅具有元素**thisuser**。</span><span class="sxs-lookup"><span data-stu-id="1514b-107">Use the **userid** and **password** elements only with **thisuser**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1514b-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="1514b-108">See Also</span></span>  
 [<span data-ttu-id="1514b-109">MQSeries 适配器的无提示配置</span><span class="sxs-lookup"><span data-stu-id="1514b-109">Silent Configuration of the MQSeries Adapter</span></span>](../core/silent-configuration-of-the-mqseries-adapter.md)