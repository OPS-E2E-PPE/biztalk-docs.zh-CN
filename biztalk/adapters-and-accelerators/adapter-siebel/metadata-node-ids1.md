---
title: BizTalk 适配器包中的 Siebel 适配器的元数据节点 Id |Microsoft Docs
description: 元数据，搜索、 检索节点类型和在 Siebel 适配器的 BizTalk 适配器包 (BAP) 中公开的 Siebel 组件中使用的 Id
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bdffc8d1-0a0a-48d7-b134-5d16acf2c523
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: abce1288be6c706d71bf644325a9cfd7200155c4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991478"
---
# <a name="node-types-and-ids-for-the-siebel-adapter"></a>节点类型和 Siebel 适配器的 Id

## <a name="metadata-node-types-and-ids"></a>元数据节点类型和 Id 
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]以分层方式显示 Siebel 系统项目。 下表描述的节点类型和显示的 Siebel 项目的节点 Id [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。  


|                项目                 | 节点类型 |                                 节点 Id                                  |                                          示例                                          |                                  Description                                   |
|-----------------------------------------|-----------|--------------------------------------------------------------------------|-------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------|
| 业务对象 （所有业务对象） | 类别  |                        [VERSION] / BusinessObjects                         |                http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects                |                         返回所有业务对象。                          |
|          业务对象 (BO)           | 类别  |                      [VERSION] /BusinessObjects/ [BO]                      |            http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account            | 返回与指定的业务对象相关联的所有业务组件。 |
|         业务组件 (BC)         | 类别  |                   [VERSION] /BusinessObjects/ [BO] / [BC]                    |        http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account        |    返回与指定的业务组件关联的所有操作。    |
|                 Insert                  | OPERATION |                [VERSION]/BusinessObjects/[BO]/[BC]/Insert                |    http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert     |       返回指定的业务组件的插入操作。       |
|                  查询                  | OPERATION |                [VERSION]/BusinessObjects/[BO]/[BC]/Query                 |     http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Query     |       返回指定的业务组件查询操作。        |
|                 Update                  | OPERATION |                [VERSION]/BusinessObjects/[BO]/[BC]/Update                |    http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Update     |       返回指定的业务组件的更新操作。       |
|                 DELETE                  | OPERATION |                [VERSION]/BusinessObjects/[BO]/[BC]/Delete                |    http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Delete     |       返回指定的业务组件的删除操作。       |
|                将相关联                | OPERATION |              [VERSION]/BusinessObjects/[BO]/[BC]/Associate               |   http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Associate   |     返回指定的业务组件的关联操作。      |
|               取消关联                | OPERATION |              [VERSION]/BusinessObjects/[BO]/[BC]/Dissociate              |  http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Dissociate   |     返回指定的业务组件取消关联操作。     |
|  Query_ [在包含 MVG 子业务组件]   | OPERATION | [VERSION] /BusinessObjects/ [BO] / [BC] / Query_ [在包含 MVG 子业务组件] | http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Query_Contact |          返回子业务组件的查询操作          |
|            业务服务            | 类别  |                        [VERSION] / BusinessServices                        |               http://Microsoft.LobServices.Siebel/2007/03/BusinessServices                |                         返回所有业务服务。                         |
|            业务服务             | 类别  |              [VERSION] /BusinessServices/ [业务服务]               |             http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/ATP              |        返回指定的业务服务的所有业务方法。        |
|         业务服务方法         | OPERATION | [VERSION] /BusinessServices/ [业务服务] / [业务服务方法]  |       http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/ATP/ATPRunCheck        |                 返回指定的业务服务方法。                 |

 [VERSION] =; 在版本字符串例如http://Microsoft.LobServices.Siebel/2007/03。  

 [BO] = Siebel 业务对象;例如，帐户。  

 [BC] = 业务组件;例如，帐户。  

 [业务服务] = Siebel 业务服务;例如，ATP。  

 [业务服务方法] = 的一种业务服务; 方法例如，DismissAlarm。  

 [在包含 MVG 子业务组件] = 多值组子业务组件;例如，请联系。  

## <a name="metadata-search-and-node-ids"></a>元数据搜索和节点 Id  
 元数据搜索是一项强大功能[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]图面作为的一部分其**MetadataRetrievalContract**接口。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]利用此功能以支持搜索以下的 Siebel 项目。  

|项目|节点 Id|Description|  
|--------------|-------------|-----------------|  
|业务对象|[VERSION] / BusinessObjects|返回与搜索表达式匹配的业务对象。|  
|业务组件|[VERSION] /BusinessObjects/ [BO]|返回与搜索表达式匹配的业务组件。|  
|业务服务|[VERSION] / BusinessServices|返回与搜索表达式匹配的业务服务。|  
|业务服务方法|[VERSION] /BusinessServices/ [业务服务]|返回与搜索表达式匹配的业务服务方法。|  

 [VERSION] =; 在版本字符串例如http://Microsoft.LobServices.Siebel/2007/03。  

 [BO] = Siebel 业务对象;例如，帐户。  

 [业务服务] = Siebel 业务服务;例如，ATP。  

 对于有效的搜索表达式，请参阅 Siebel 文档。  

> [!NOTE]
>  [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]仅支持在当前所选节点下的级别的搜索。  例如，选中 BusinessObjects 后，A * 是支持搜索，但一个\*/A\*不是。  

## <a name="metadata-retrieval-and-node-ids"></a>元数据检索和节点 Id  
 Siebel 适配器捕获每种类型的项目的以下特征。  

|项目|元数据特征|  
|--------------|------------------------------|  
|业务组件|<ul><li>业务组件名称</li><li>业务组件字段名称</li><li>业务组件字段数据类型映射到简单/复杂 WSDL 类型</li><li>映射到 facet maxLength 业务组件字段长度</li><li>业务组件必填字段映射到 facet minOccurs = 1</li><li>业务组件可选字段映射到 facet minOccurs = 0</li><li>业务组件选择列表字段映射到 WSDL 中的选择列表复杂类型</li><li>业务组件静态绑定选择列表包含值的枚举的列表</li><li>业务组件字段 NULL 约束映射到 facet isNillable = true</li><li>业务组件操作<br /><br /> <ul><li>Insert</li><li>QUERY</li><li>UPDATE</li><li>删除</li><li>将相关联</li><li>取消关联</li><li>为每个业务组件与有 m:n 关系的子业务组件 QUERY_ [在包含 MVG 子业务 Comp]</li></ul></li></ul>|  
|业务服务方法|线业务服务名称<br />方法名称<br />方法是操作<br />方法参数名称<br />方法参数数据类型映射到 WSDL 类型<br />映射到 WSDL 参数方向的方法参数方向<br />映射到元素序列的方法参数顺序|  

 有关格式的元数据的详细信息，[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]公开特定项目和操作在 Siebel 系统中，请参阅[消息和用于 Siebel eBusiness 应用程序的BizTalk适配器的消息架构](../../adapters-and-accelerators/adapter-siebel/messages-and-message-schemas-for-siebel-adapter-in-biztalk.md).  
