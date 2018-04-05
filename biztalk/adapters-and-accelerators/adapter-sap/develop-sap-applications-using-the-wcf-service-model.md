---
title: 开发使用 WCF 服务模型的 SAP 应用程序 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, developing applications
ms.assetid: 5387d063-31d3-49b3-9771-354802542f8f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4933610f8416b2c7fb81861562480e355dd8d373
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="develop-sap-applications-using-the-wcf-service-model"></a>开发使用 WCF 服务模型的 SAP 应用程序
在最低级别，[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]提供一个在其中客户端调用服务上的操作通过在客户端和服务终结点之间建立信道交换 SOAP 消息的编程模型。 此模型中，称为 WCF 通道模型，公开数据类型和方法，您可以直接对 WCF 通道体系结构进行操作。 WCF 通道模型为您提供通过你创建的 SOAP 消息的内容和方式这两个应用程序的直接控制和[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用它们; 但是，创建格式正确的 SOAP 消息在通道上发送和验证返回答复消息可以是详细、 更严格的任务。  
  
 为此，[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供另一个调用 WCF 服务模型的编程模型。 WCF 服务模型涉及使用代理类来调用针对目标服务的操作或从客户端接收操作。  
  
-   用于调用操作将针对目标服务的代理类调用 WCF 客户端类。 此类模型作为使用强类型参数的.NET 方法由服务公开的操作。 通过使用 WCF 服务模型，你可以调用公开的运算[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]为 WCF 客户端上的.NET 方法。 有关 WCF 客户端的详细信息，请参阅[WCF 客户端概述](https://msdn.microsoft.com/library/ms735103.aspx)。
  
-   用于从客户端接收操作的代理类调用 WCF 服务协定类。 此类模型作为具有强类型参数的回调方法的代码公开的操作。 然后可以托管在此类的实例**System.ServiceModel.ServiceHost**使客户端以调用你的代码上的操作。 可以通过使用 WCF 服务模型和指向 POLLINGSTMT 操作一个 WCF 服务协定类，接收从轮询查询的结果[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
 使用工具来生成 WCF 客户端类或 WCF 服务协定和关联的服务元数据中的帮助器代码，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]公开。 你可以使用以下工具之一：  
  
-   ServiceModel 元数据实用工具 (svcutil.exe)，其中附带 WCF  
  
-   [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]，其中附带[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]  
  
 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]与集成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]设计体验和显示标准的 Microsoft Windows 接口提供了功能强大的浏览和搜索功能公开的适配器操作。 有关如何生成 WCF 客户端或 WCF 服务协定类的详细信息，请参阅[生成 WCF 客户端或 WCF 服务协定 SAP 解决方案项目](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)。  
  
 因为它提供的模型，可为.NET 程序员所熟悉和，以通过通道隐藏基础 SOAP 消息交换的复杂性，WCF 服务模型通常是最佳选择，以编程的开发解决方案[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 但是，有在其中 WCF 通道模型可能是更好的选择; 的方案特别是在中哪种流式处理方案非常重要。 这是因为序列化和反序列化的 XML 表示形式在 SOAP 消息的对象和用于表示它们的服务模型中的.NET 类型之间涉及到读取到内存的整个消息。 有关使用 WCF 通道模型的详细信息，请参阅[开发 SAP 应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)。
  
 本部分中的主题包含信息、 过程和示例来帮助你创建并使用 WCF 服务模型来开发应用程序使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [与 SAP 适配器的 WCF 服务模型概述](../../adapters-and-accelerators/adapter-sap/overview-of-the-wcf-service-model-with-the-sap-adapter.md)  
  
-   [元数据和 WCF 服务模型与 SAP](../../adapters-and-accelerators/adapter-sap/metadata-and-the-wcf-service-model-with-sap.md)  
  
-   [生成 WCF 客户端或 WCF 服务协定 SAP 解决方案项目](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)  
  
-   [为 SAP 系统配置客户端绑定](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md)  
  
-   [使用 WCF 服务模型调用中 SAP Rfc](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-the-wcf-service-model.md)  
  
-   [通过使用 WCF 服务模型在 SAP 中收到入站的 RFC 调用](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-in-sap-using-the-wcf-service-model.md)  
  
-   [使用 WCF 服务模型调用 tRFCs](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-the-wcf-service-model.md)  
  
-   [通过使用 WCF 服务模型在 SAP 中收到入站的 tRFC 调用](../../adapters-and-accelerators/adapter-sap/receive-inbound-trfc-calls-in-sap-using-the-wcf-service-model.md)  
  
-   [使用 WCF 服务模型调用 BAPIs SAP 中](../../adapters-and-accelerators/adapter-sap/invoke-bapis-in-sap-using-the-wcf-service-model.md)  
  
-   [使用 WCF 服务模型将 Idoc 发送到 SAP](../../adapters-and-accelerators/adapter-sap/send-idocs-to-sap-using-the-wcf-service-model.md)