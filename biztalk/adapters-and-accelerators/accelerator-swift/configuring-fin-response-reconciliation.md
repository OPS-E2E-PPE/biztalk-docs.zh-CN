---
title: "配置 FIN 响应对帐 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FIN Response Reconciliation, configuring
- configuring, FIN Response Reconciliation
ms.assetid: dc934530-76ff-4cdb-b182-46f9ea0343b7
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 384a2ea27e3d208864c8b16ec52562e6e1cfa28e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-fin-response-reconciliation"></a>配置 FIN 响应对帐
你必须在以下部分来配置中执行步骤[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] FIN 响应对帐 (FRR) 功能，如下图中所示。  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-frr-configuration.jpg "A4SWIFT_FRR_Configuration")  
  
 在 A4SWIFT 安装向导中，你可以选择安装消息修复和新的提交和 FRR，或消息修复和新的提交，而无需 FRR 或如果没有消息修复和新提交 FRR。 因此，本部分中的说明进行操作不会假定安装和配置消息修复和新的提交。 它们，但是，假定你已执行中的步骤[A4SWIFT 运行时配置](../../adapters-and-accelerators/accelerator-swift/configuring-the-a4swift-runtime.md)。  
  
 本部分包含：  
  
-   [绑定和启动 FRR 业务流程](../../adapters-and-accelerators/accelerator-swift/binding-and-starting-the-frr-orchestration.md)  
  
-   [创建 FRR 接收管道](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-receive-pipeline.md)  
  
-   [创建 FRR 接收位置用于接收从后端应用程序](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-receive-location-for-receiving-from-the-back-end-application.md)  
  
-   [创建 FRR 来接收来自 SWIFT 接收位置](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-receive-location-for-receiving-from-swift.md)  
  
-   [创建 FRR 发送管道](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-pipeline.md)  
  
-   [创建用于将发送到 SWIFT FRR 发送端口](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-port-for-sending-to-swift.md)  
  
-   [创建 FRR 发送端口将发送到自定义处理程序](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md)