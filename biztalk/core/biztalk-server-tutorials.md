---
title: BizTalk Server 教程 |Microsoft 文档
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
ms.openlocfilehash: f13a5d74d0957a208600653823e7604680296f4d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232069"
---
# <a name="biztalk-server-tutorials"></a>BizTalk Server 教程
教程以了解如何使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。

BizTalk Server 教程包含一些简单的方案，以便新用户体验如何在创建编译好的可测试集成解决方案时使用各种 BizTalk 工具。 对于更高级的用户或 BizTalk 解决方案设计的用户，请参阅[商业解决方案的方案](../core/scenarios-for-business-solutions.md)。  
  
## <a name="enterprise-application-integration"></a>企业应用程序集成
  
[教程： 企业应用程序集成](../core/tutorial-1-enterprise-application-integration.md) 

实现 BizTalk 解决方案，其接收来自仓库库存补货请求消息并对请求消息进行计算。 如果解决方案拒绝请求，然后发送拒绝消息到仓库。 如果解决方案批准请求，然后它将消息转发到企业资源规划 (ERP) 系统。  

## <a name="create-a-hybrid-application"></a>创建混合应用程序
[教程： 创建混合应用程序使用 BizTalk Server](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)  

设置的端到端应用程序使用 EDI 来生成的确认，Service Bus 接收消息，然后再将数据插入到 SQL。 

## <a name="invoke-a-rest-interface"></a>调用 REST 接口
[教程： 调用 REST 接口使用 BizTalk Server](../core/tutorial-5-invoking-a-rest-interface-using-biztalk-server.md)  

使用 WCF WebHttp 适配器使用 REST 的 URL，并随后发送响应消息。 

## <a name="integrate-biztalk-with-salesforce"></a>将与 Salesforce 集成 BizTalk
[教程： 将与 Salesforce 集成 BizTalk Server](Tutorial:%20Integrating%20BizTalk%20Server%202013%20with%20Salesforce.md)  

每次创建销售机会时 Salesforce 系统中，Northwind 希望其本地系统，例如 BizTalk Server 中，若要得到通知，以便其他下游系统可以选取该数据并启动其他相关的进程。 

## <a name="process-json-messages"></a>处理 JSON 消息
[使用 BizTalk Server 处理 JSON 消息](../core/processing-json-messages-using-biztalk-server.md)  

设置 BizTalk 应用程序接收 JSON 采购订单。 在接收管道 JSON 解码器组件 JSON 消息转换为 XML 消息。 然后，使用地图将转换为 XML 发票 XML 采购订单。 发送管道使用 JSON 编码器可以将 XML 发票转换为 JSON 发票，然后将消息发送。

## <a name="edi-interface-developer"></a>EDI 接口开发人员
  [教程： EDI 接口开发人员教程](../core/tutorial-2-edi-interface-developer-tutorial.md)
  
贸易合作伙伴发送采购订单使用 ANSI X12 4010 850 事务集 （850 消息）。 内部顺序系统进程采购订单。

作为接口开发人员负责设计 850 消息之间的接口，你收到从贸易合作伙伴和公司的内部顺序系统。 你的贸易合作伙伴要求为发送的每条 850 消息获得一个功能确认 (997)。


## <a name="as2"></a>AS2  
[教程： AS2 教程](../core/tutorial-3-as2-tutorial.md)

将设置为接收和发送编码 EDIINT/AS2 消息通过 HTTP 传输的解决方案。    


## <a name="do-more"></a>执行更多操作  
 若要了解有关 BizTalk Server 概念和体系结构的详细信息，请考虑以下：  
  
[入门](../core/getting-started-with-biztalk-server.md)
  
[规划和设计你的 BizTalk Server 解决方案](../core/plan-and-architect-your-biztalk-server-solution.md)