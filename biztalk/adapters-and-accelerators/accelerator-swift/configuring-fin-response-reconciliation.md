---
title: 配置 FIN 响应对帐 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FIN Response Reconciliation, configuring
- configuring, FIN Response Reconciliation
ms.assetid: dc934530-76ff-4cdb-b182-46f9ea0343b7
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77f2260c8e6096e2bef926fea45aaf778f4bdfa3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997902"
---
# <a name="configuring-fin-response-reconciliation"></a>配置 FIN 响应对帐
必须执行以下各节中，若要配置 Microsoft 中的步骤[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]FIN 响应对帐 (FRR) 功能，如下图中所示。  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-frr-configuration.jpg "A4SWIFT_FRR_Configuration")  
  
 在 A4SWIFT 安装向导中，您可以选择安装消息修复和新提交以及 FRR，或消息修复和新提交，而无需 FRR 或如果没有消息修复和新提交的 FRR。 因此，在本部分中的说明进行操作不要假定您在安装和配置消息修复和新提交。 它们执行操作，但是，假设已执行中的步骤[配置 A4SWIFT 运行时](../../adapters-and-accelerators/accelerator-swift/configuring-the-a4swift-runtime.md)。  
  
 本部分包含：  
  
-   [绑定和启动 FRR 业务流程](../../adapters-and-accelerators/accelerator-swift/binding-and-starting-the-frr-orchestration.md)  
  
-   [创建 FRR 接收管道](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-receive-pipeline.md)  
  
-   [创建从后端应用程序接收的 FRR 接收位置](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-receive-location-for-receiving-from-the-back-end-application.md)  
  
-   [创建从 SWIFT 接收的 FRR 接收位置](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-receive-location-for-receiving-from-swift.md)  
  
-   [创建 FRR 发送管道](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-pipeline.md)  
  
-   [创建发送到 SWIFT 的 FRR 发送端口](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-port-for-sending-to-swift.md)  
  
-   [创建发送到自定义图柄的 FRR 发送端口](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md)