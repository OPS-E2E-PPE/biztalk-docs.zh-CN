---
title: BizTalk Server 教程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tutorials, getting started
- getting started, tutorials
ms.assetid: 58019f98-e91a-4705-b689-c269174d6bae
caps.latest.revision: 42
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66b3aad058d6d1ecbc40a62de5b73eab8aea43ec
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530387"
---
# <a name="biztalk-server-tutorials"></a>BizTalk Server 教程
教程，了解如何使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。

BizTalk Server 教程包含简单的方案以便新用户体验如何在创建编译可测试集成解决方案时使用的各种 BizTalk 工具。 对于更高级的用户或设计 BizTalk 解决方案的用户，请参阅[业务解决方案的方案](../core/scenarios-for-business-solutions.md)。  
  
## <a name="enterprise-application-integration"></a>企业应用程序集成
  
[教程：企业应用程序集成](../core/tutorial-1-enterprise-application-integration.md) 

实现一个 BizTalk 解决方案，从仓库接收库存补货请求消息并对请求消息进行评估。 如果该解决方案拒绝请求，然后它将发送拒绝消息到仓库。 如果解决方案批准请求，然后它将消息转发到企业资源规划 (ERP) 系统。  

## <a name="create-a-hybrid-application"></a>创建混合应用程序
[教程：创建混合应用程序使用 BizTalk Server](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)  

设置端到端应用程序使用 EDI 用于生成确认，服务总线接收消息，然后再将数据插入到 SQL。 

## <a name="invoke-a-rest-interface"></a>调用 REST 接口
[教程：调用 REST 接口使用 BizTalk Server](../core/tutorial-5-invoking-a-rest-interface-using-biztalk-server.md)  

使用 Wcf-webhttp 适配器要使用某个 REST URL，然后发送响应消息。 

## <a name="integrate-biztalk-with-salesforce"></a>将 BizTalk 与 Salesforce 集成
[教程：将 BizTalk Server 与 Salesforce 集成](Tutorial:%20Integrating%20BizTalk%20Server%202013%20with%20Salesforce.md)  

每次在 Salesforce 系统中创建销售机会时，Northwind 希望其在本地系统，例如 BizTalk Server 接收通知，以便其他下游系统可以提取该数据并启动其他相关进程。 

## <a name="process-json-messages"></a>处理 JSON 消息
[使用 BizTalk Server 处理 JSON 消息](../core/processing-json-messages-using-biztalk-server.md)  

设置接收 JSON 采购订单的 BizTalk 应用程序。 在接收管道中，JSON 解码器组件将 JSON 消息转换为 XML 消息。 然后，使用映射将 XML 采购订单转换为 XML 发票。 发送管道使用 JSON 编码器将 XML 发票转换为 JSON 发票，并再将该消息。

## <a name="edi-interface-developer"></a>EDI 接口开发人员
  [教程：EDI 接口开发人员教程](../core/tutorial-2-edi-interface-developer-tutorial.md)
  
贸易合作伙伴发送采购订单使用 ANSI X12 4010 850 事务集 （条 850 消息）。 内部订单系统进程采购订单。

作为负责设计 850 消息之间的接口的接口开发人员，您将收到从您的贸易合作伙伴和您的公司内部的订单系统。 您的贸易合作伙伴要求为发送每条 850 消息功能确认 (997)。


## <a name="as2"></a>AS2  
[教程：AS2 教程](../core/tutorial-3-as2-tutorial.md)

设置接收并通过 HTTP 传输发送 EDIINT/AS2 编码的消息的解决方案。    


## <a name="do-more"></a>执行更多操作  
 若要了解有关 BizTalk Server 概念和体系结构的详细信息，请考虑以下：  
  
[入门](../core/getting-started-with-biztalk-server.md)
  
[计划和构建 BizTalk Server 解决方案](../core/plan-and-architect-your-biztalk-server-solution.md)