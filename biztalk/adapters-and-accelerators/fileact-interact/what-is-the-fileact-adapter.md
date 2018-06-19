---
title: 什么是 FileAct 适配器？ | Microsoft Docs
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
ms.openlocfilehash: 62b83fc723bbebce857eb442384b14179c1072ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225317"
---
# <a name="what-is-the-fileact-adapter"></a>什么是 FileAct 适配器？
SWIFTNet FileAct 适配器提供 BizTalk Server 和互联网协会之间的连接的全球 Interbank 财务电信 (SWIFT) 保护 IP 网络 (SIPN) 传输的文件。 SIPN 连接金融机构、 金融业基础结构和客户的安全专用网络上传输消息和文件。 FileAct 适配器使用 SWIFTNet 链接 (SNL) 应用程序编程接口 (API) s 要连接到 SIPN。  
  
 FileAct 适配器 SWIFT 参加安全地提供一种机制，并可靠地交换文件和与这些文件相关的信息。 它支持以下功能：  
  
-   将文件发送到 SWIFTNet 用户  
  
-   从 SWIFTNet 用户检索文件  
  
-   确认接收方接收的文件传递通知  
  
-   中止的正在进行的传输  
  
-   文件传输状态监视  
  
-   并发文件传输  
  
-   数据的真实性和完整性保证  
  
-   在传输过程中的文件数据保密性  
  
-   不可否认性的文件传输  
  
-   时间戳  
  
## <a name="the-fileact-service"></a>FileAct 服务  
 SWIFTNet FileAct 适配器提供安全且可靠传输文件，如批次的结构化的财务消息或大型报表。 典型的应用程序包括如退休金或设置薪金支付、 有价证券增值信息和报告和监管报告的重复的信用额度传输。 SWIFTNet FileAct 提供各种消息传递模式：  
  
-   **存储转发文件传输。** SWIFTNet FileAct 存储转发功能中删除的不确定性和不便担心你的通讯对象都处于联机状态时传输该文件。 一旦接收方准备好接收它，则传递该文件。 因此，它提供将文件发送到大量通讯对象，其中一些可能在不同时区的理想途径。  
  
-   **实时文件传输。** 实时消息传递提供的成本较低的替代方法存储和转发的以在传输时处于联机状态的通讯对象为目标的文件。 因此它非常适合用于将文件发送到几大通讯对象或市场基础结构。  
  
-   **实时文件检索。** 这是通常用于检索基于工作站的系统上下文中并通常与 SWIFTNet 浏览结合使用的文件交互服务。 我们将支持此模式。  
  
 （基于文件的文件发生） 的可选 SWIFTNet FileAct 功能包括：  
  
-   **消息优先级。** 在消息中，以允许适当处理你的通讯对象，可以将文件传输标记为"紧急"。  
  
-   **传递通知 （实时和存储转发模式）。** 提供你通信者收到你的文件的确认消息。  
  
-   **不可否认性发出和接收。** 发生争议，允许 SWIFT 以确认所声称的那个，传输未成功进行。  
  
 标准 SWIFTNet FileAct 功能包括 SWIFTNet PKI 安全性 **。** SWIFTNet FileAct 使用 SWIFTNet PKI 进行了保护，并提供消息身份验证和完整性控件。  
  
 所有消息和交换 SWIFTNet 上的文件都对一组通用的检查，以确保安全、 验证和平台的路由规则没有用户可以绕过。 SWIFTAlliance 网关 （压降） 应用程序执行这些检查。  
  
## <a name="see-also"></a>另请参阅  
 [Getting Started with FileAct 和交互适配器](../../adapters-and-accelerators/fileact-interact/getting-started-with-the-fileact-and-interact-adapters.md)   
 [什么是 SWIFTNet？](../../adapters-and-accelerators/fileact-interact/what-is-swiftnet.md)   
 [什么是交互适配器？](../../adapters-and-accelerators/fileact-interact/what-is-the-interact-adapter.md)