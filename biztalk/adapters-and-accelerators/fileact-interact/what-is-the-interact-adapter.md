---
title: 什么是交互适配器？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a09063df-c6c4-41b9-96a1-e5059777fa72
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25877b95a440faef802d3d2ba7861687d7e4b108
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224749"
---
# <a name="what-is-the-interact-adapter"></a>什么是交互适配器？
SWIFTNet 交互适配器传输的消息提供 BizTalk Server 和 SWIFT 保护 IP 网络 (SIPN) 之间的连接。 SIPN 互连金融机构、 金融业基础结构和客户的安全专用网络上传输消息和文件。 交互适配器使用 SWIFTNet 链接 (SNL) 应用程序编程接口 (API) s 要连接到 SIPN。  
  
 SWIFTNet 交互提供安全、 可靠单个结构化的财务消息交换。 客户客户，但还从消息到消息，SWIFT 客户的消息传送要求各不相同。  
  
 它支持以下功能：  
  
-   PKI 安全性  
  
-   消息验证  
  
-   可配置的中央路由  
  
-   消息优先级  
  
-   应用商店应用和转发的消息传递通知  
  
-   不可否认性发出和接收。  
  
 使用交互适配器 SWIFTNet 与外部提供的应用程序以利用交互的功能。 此适配器程序不知道要传输，并将审核或未验证的消息，但 exchange 基元除外的内容的消息的内容。  
  
## <a name="interact-message-exchange"></a>交互消息交换  
 SWIFTNet 交互提供安全、 可靠单个结构化的财务消息交换。 客户客户，但还从消息到消息，SWIFT 客户的消息传送要求各不相同。 SWIFTNet 交互提供广泛的电信模式：  
  
-   **存储转发消息传送。** SWIFTNet 交互的存储和转发功能旨在用于消息发送到大量的通讯对象，其中许多员工可能不处于联机状态的传输时间。 它会删除的不确定性和不便担心你的通讯对象处于联机状态时发送消息。 一旦接收方准备好接收它，邮件将被传递。 因此，它提供了将单个说明、 确认和报表发送到大量通讯对象，其中一些可能在不同时区的理想途径。  
  
-   **实时消息传递。** 实时消息传递提供低成本替代对其进行存储和转发的消息都以在传输时处于联机状态的通讯对象为目标。 因此，它非常适合于发送单个说明、 确认和报表，为几大通讯对象或消息推向市场基础结构。  
  
 （在消息的消息的基础） 的可选 SWIFTNet 交互功能包括：  
  
-   **消息优先级。** 在消息中，以允许适当处理你的通讯对象，可以将消息标记为"紧急"。  
  
-   **传递通知 （存储转发模式）。** 提供你通信者接收消息的确认  
  
-   **不可否认性发出和接收。** 发生争议，允许 SWIFT 以确认的消息交换未进行，所声称的那个。  
  
 标准 SWIFTNet 交互功能包括 SWIFTNet PKI 安全性。 SWIFTNet FileAct 使用 SWIFTNet PKI 进行了保护，并提供消息身份验证和完整性控件。  
  
 所有消息和交换 SWIFTNet 上的文件都对一组通用的检查，以确保安全、 验证和平台的路由规则没有用户可以绕过。 SWIFTAlliance 网关 （压降） 应用程序执行这些检查。  
  
## <a name="see-also"></a>另请参阅  
 [Getting Started with FileAct 和交互适配器](../../adapters-and-accelerators/fileact-interact/getting-started-with-the-fileact-and-interact-adapters.md)   
 [什么是 SWIFTNet？](../../adapters-and-accelerators/fileact-interact/what-is-swiftnet.md)   
 [什么是 FileAct 适配器？](../../adapters-and-accelerators/fileact-interact/what-is-the-fileact-adapter.md)