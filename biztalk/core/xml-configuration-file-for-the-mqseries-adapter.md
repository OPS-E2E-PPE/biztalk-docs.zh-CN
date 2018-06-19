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
# <a name="xml-configuration-file-for-the-mqseries-adapter"></a>MQSeries 适配器的 XML 配置文件
XML 配置文件读取**mqsconfigwiz**包含用户输入时使用该向导的 Windows 版本的相同信息。 此信息包括应用程序标识以及用户 ID 和密码（如果需要）、角色名称，以及该角色所包含用户的列表。  
  
 该文件的示例如下所示：  
  
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
  
 你可以使用**thisuser**， **InteractiveUser**， **LocalService**，或**NetworkService**一样的值**AppIdentity**. 使用**userid**和**密码**仅具有元素**thisuser**。  
  
## <a name="see-also"></a>另请参阅  
 [无提示 MQSeries 适配器配置](../core/silent-configuration-of-the-mqseries-adapter.md)