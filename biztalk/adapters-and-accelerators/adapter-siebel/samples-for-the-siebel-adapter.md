---
title: Siebel 适配器示例 |Microsoft Docs
description: 可以使用 BizTalk Server、 WCF 服务模型和数据访问接口使用 siebel 的 Siebel WCF 适配器示例
ms.custom: ''
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 069d676e-211e-474c-9cf5-c660fdd22014
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57b338fd5cb445d8d83e9d3d364909cf7a9eb6b5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371032"
---
# <a name="samples-for-the-siebel-adapter"></a>Siebel 适配器的示例
示例[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]分为：  

- [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 示例  

- WCF 服务模型示例  

- [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] 示例  


这些示例是在[BizTalk 适配器包 2010年:Siebel 适配器示例](https://www.microsoft.com/download/details.aspx?id=6492)。 

> [!NOTE]
> [!INCLUDE[files-need-updated](../../includes/files-need-updated.md)]

以下列表说明的示例。

## <a name="biztalk-server-samples"></a>BizTalk Server 示例  

|      示例目录名称      |                                                                                     Description                                                                                     |
|---------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|         BusinessService         |                    演示如何调用中使用 Siebel 业务服务[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。                     |
|             MVLDemo             |                演示如何使用在 Siebel 中使用的多值链接 (MVLs) [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。                 |
|          SiebelAccount          |        演示如何将记录插入到在 Siebel 中使用的帐户业务组件[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。        |
| SiebelAdapterIntegrationObjects | 演示如何调用中可用于集成对象，使用 Siebel 业务服务[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。 |
|         SiebelPicklist          |      演示如何将选择列表类型的值插入到 Siebel 业务组件使用[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。      |

## <a name="wcf-service-model-samples"></a>WCF 服务模型示例 

|示例目录名称|Description|  
|---------------------------|-----------------|  
|AccountInsertDelete|演示如何执行插入、 更新、 删除和查询在 Siebel 业务组件上的操作。 此示例帐户业务对象的帐户业务组件中插入一条记录，更新的记录，并最终将其删除。 每个操作之前和之后要验证结果的业务组件执行查询操作。|  
|业务服务|演示如何调用 Siebel 业务服务方法，时间戳，并将结果显示到控制台。|  
|MVL|演示如何通过使用关联、 取消关联和子查询操作使用 Siebel 业务组件中的多值链接。 示例将显示与帐户关联的所有联系人。 它还显示了如何关联和取消关联帐户中的联系人。|  

## <a name="data-provider-for-siebel-sample"></a>用于 Siebel 示例数据提供程序  

| 示例目录名称 |                                                Description                                                 |
|-----------------------|------------------------------------------------------------------------------------------------------------|
|      siebel ado       | 演示如何使用[!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)]。 |

## <a name="see-also"></a>请参阅  
[开发 Siebel 应用程序](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)