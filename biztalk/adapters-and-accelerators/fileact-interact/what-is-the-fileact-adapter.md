---
title: FileAct 适配器是什么？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 05ec8f1e-57f9-4e2d-ab8b-22b5c4b28055
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d810ded6d5a73b2f22e04e3e27a15684bb55a09
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364051"
---
# <a name="what-is-the-fileact-adapter"></a>FileAct 适配器是什么？
SWIFTNet FileAct 适配器之间提供连接 BizTalk Server 和在全球范围内 Interbank 金融电信 (SWIFT) Secure IP Network (SIPN) 为传输的文件。 SIPN 连接金融机构、 金融业基础结构和客户的安全专用网络上传输消息和文件。 FileAct 适配器使用 SWIFTNet 链接 (SNL) 应用程序编程接口 (API) s 要连接到 SIPN。  
  
 FileAct 适配器安全地向 SWIFT 参与者提供一种机制，并可靠地交换文件和与这些文件相关的信息。 它支持以下功能：  
  
-   将文件发送给 SWIFTNet 用户  
  
-   从 SWIFTNet 用户检索文件  
  
-   送达通知确认由接收方接收的文件  
  
-   中止正在进行中传输的  
  
-   文件传输状态监视  
  
-   并发文件传输  
  
-   确保数据的真实性和完整性的情况  
  
-   在传输过程中的文件数据的机密性  
  
-   文件传输的不可否认性  
  
-   时间戳  
  
## <a name="the-fileact-service"></a>FileAct 服务  
 SWIFTNet FileAct 适配器提供文件，如批次的结构化的财务消息或大型报表的安全且可靠的传输。 典型的应用程序包括重复的信用额度传输如养老金或薪金付款、 证券增值信息报告和法规报告。 SWIFTNet FileAct 提供各种消息传送模式：  
  
- **存储和转发文件传输。** SWIFTNet FileAct 存储和转发功能删除的不确定性和不便的担心在帖者都处于联机状态时传输文件。 接收方已准备好接收它，该文件是立即传递。 因此，它提供将文件发送到大量的帖者，其中一些可能在不同时区的理想方式。  
  
- **实时文件传输。** 实时消息传送提供成本较低的替代方法来存储和转发目标为帖者，在传输时处于联机状态的文件。 因此它非常适合用于将文件发送到几个大型帖者或市场的基础结构。  
  
- **实时文件检索。** 这是通常用于检索文件的基于工作站的系统上下文中，通常是在与 SWIFTNet 浏览一起交互服务。 我们将支持此模式。  
  
  （以文件的文件为单位） 的可选 SWIFTNet FileAct 功能包括：  
  
- **消息优先级。** 文件传输可以在消息中，以允许适当处理你的通讯对象标记为"紧急"。  
  
- **送达通知 （实时和存储转发模式）。** 提供对响应方返回收到你的文件的确认消息。  
  
- **发出和接收的不可否认。** 争议，如果允许 SWIFT 以确认所声称的那个，传输未成功进行。  
  
  标准 SWIFTNet FileAct 功能包括 SWIFTNet PKI 安全性<strong>。</strong> SWIFTNet FileAct SWIFTNet pki 保护，并提供消息身份验证和完整性控制。  
  
  所有消息以及交换 SWIFTNet 上的文件会都进行一组通用的检查，以确保安全、 验证和平台的路由规则没有用户可以绕过。 SWIFTAlliance 网关 （压降） 应用程序执行这些检查。  
  
## <a name="see-also"></a>请参阅  
 [开始使用 FileAct 和 InterAct 适配器](../../adapters-and-accelerators/fileact-interact/getting-started-with-the-fileact-and-interact-adapters.md)   
 [SWIFTNet 是什么？](../../adapters-and-accelerators/fileact-interact/what-is-swiftnet.md)   
 [InterAct 适配器概述](../../adapters-and-accelerators/fileact-interact/what-is-the-interact-adapter.md)