---
title: 端口配置错误 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 92eae0d8-a0c4-4f8c-b91a-fd98b9f6931a
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f0e51c06fab9dadb60fc43a003108e50bbb0fab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264189"
---
# <a name="port-configuration-errors"></a>端口配置错误
用于诊断和解决 WCF 端口配置错误的信息。  

## <a name="cannot-merge-operation-due-to-communication-pattern-conflict"></a>由于通信模式冲突，无法合并操作
  
||详细信息|  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|事件 ID|0|  
|事件源|0|  
|组件|0|  
|符号名称|0|  
|消息正文|由于通信模式冲突而无法合并操作“{0}”。  所有操作都必须是单向或请求响应模式|  
  
### <a name="explanation"></a>解释  
 此错误表示 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 正尝试合并端口类型具有不同通信模式的端口。  
  
### <a name="user-action"></a>用户操作  
 使用端口配置向导，确保要合并的所有端口都拥有相同的通信方向，即单向或请求响应模式。  
  
 有关端口配置的其他信息，请参阅[如何运行端口配置向导](../core/how-to-run-the-port-configuration-wizard.md)。
 
## <a name="port-types-that-have-a-combination-of-one-way-and-request-response-operations-are-not-allowed"></a>端口类型拥有的单向组合，不允许请求-响应操作 
  
||详细信息|  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|事件 ID|0|  
|事件源|0|  
|组件|0|  
|符号名称|0|  
|消息正文|端口类型拥有的单向组合，不允许请求-响应操作。 更正服务说明"{0}"端口类型"{1}"，然后重新运行该向导|  
  
### <a name="explanation"></a>解释  
 此错误表示尝试使用的服务，也没有操作的单向和双向 （请求-响应）。  
  
### <a name="user-action"></a>用户操作  
 将服务更正为具有合适的操作（单向或请求响应，但不是同时具有两者），并尝试使用该服务（如果拥有要尝试使用的 WCF 服务）。 否则，请与服务提供商联系。
