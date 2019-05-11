---
title: 多个 Web 服务的示例工作原理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 16680ca7-16cc-47df-8c39-a3311d468a46
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a67e14115d404f523219b2e171f1abfba38b220
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65249773"
---
# <a name="how-the-multiple-web-services-sample-works"></a>如何在多个 Web 服务示例工作原理
多个 Web 服务示例使用两种不同方法调用中序列的多个 Web 服务，同时仍能以正确的结果返回到原始调用方。 一种方法在响应管道中，使用自定义管道组件和另一种方法使用自定义双向路由业务流程基于路线服务，绕过关闭接入点调用的完成对 Web 的请求/响应调用的要求服务。  
  
 自定义管道组件方法使用转发器管道组件。 此组件有条件地将升级属性，以防止 Microsoft BizTalk 之前处理所有路线服务，将消息路由到发送管道的好帮手。  
  
 自定义业务流程基于服务方法使用包含在 ESB TwoWayRouting 业务流程。在 \Source\Samples\MultipleWebSerivces\Source\ESB MultipleWebServices.Orchestrations 项目。MultipleWebServices.Orchestrations 文件夹。 此服务处理一个关联的冲突解决程序来确定双向的 Web 服务的终结点地址。 然后会配置名为 RoutingPort 将消息发送到 Web 服务并将结果返回到业务流程动态 Solict 响应发送端口。 业务流程然后前移路线，并生成消息返回到 MessageBox。  
  
 示例中包含的路线使用一个或两种方法来确保保留以下路线的消息流。 有关详细信息，请参阅[示例多个 Web 服务路线](../esb-toolkit/the-sample-multiple-web-services-itineraries.md)。