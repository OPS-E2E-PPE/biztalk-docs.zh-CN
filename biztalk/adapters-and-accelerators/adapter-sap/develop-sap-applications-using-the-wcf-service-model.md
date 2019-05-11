---
title: 开发 SAP 应用程序使用 WCF 服务模型 |Microsoft Docs
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
ms.openlocfilehash: f765dde8a21882d291df98bc9eebd4e9151b03b9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373506"
---
# <a name="develop-sap-applications-using-the-wcf-service-model"></a>开发 SAP 应用程序使用 WCF 服务模型
最低级别[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]显示在其中客户端调用服务上的操作由客户端和服务终结点之间建立的通道通过交换 SOAP 消息的编程模型。 此模型中，名为 WCF 通道模型，公开的数据类型和方法，使你能够直接在 WCF 通道体系结构上运行。 WCF 通道模型为您提供直接控制对您创建的 SOAP 消息的内容和方式这两个应用程序和[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用它们; 但是，创建格式正确的 SOAP 消息在通道上发送和验证返回答复消息可以是详细、 更严格的任务。  
  
 出于此原因，[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供了另一个名为 WCF 服务模型的编程模型。 WCF 服务模型涉及到使用代理类来调用目标服务上的操作，或若要从客户端接收操作。  
  
- 用于目标服务调用操作的代理类调用 WCF 客户端类。 此类模型由服务公开为强类型化参数使用的.NET 方法的操作。 通过使用 WCF 服务模型，可以调用公开的操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]为 WCF 客户端上的.NET 方法。 有关 WCF 客户端的详细信息，请参阅[WCF 客户端概述](https://msdn.microsoft.com/library/ms735103.aspx)。
  
- 用于从客户端接收操作的代理类调用 WCF 服务协定类。 此类模型具有强类型化参数的回调方法作为你的代码公开的操作。 然后可以托管在此类的实例**System.ServiceModel.ServiceHost**启用客户端以调用代码操作。 可以通过使用 WCF 服务模型和针对 POLLINGSTMT 操作的 WCF 服务协定类，接收从轮询查询的结果[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
  使用工具来生成 WCF 客户端类或 WCF 服务协定和关联的服务元数据中的帮助器代码的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]公开。 您可以使用以下工具：  
  
- ServiceModel Metadata Utility Tool (svcutil.exe)，其中附带了 WCF  
  
- [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]，附带的 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]  
  
  [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]与集成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]设计体验并提供标准的 Microsoft Windows 接口提供了功能强大的浏览和搜索功能对由适配器公开的操作。 有关如何生成 WCF 客户端或 WCF 服务协定类的详细信息，请参阅[生成 WCF 客户端或 WCF 服务约定的 SAP 解决方案项目](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)。  
  
  因为它提供的模型，这就是.NET 程序员所熟悉的和，以通过通道隐藏基础 SOAP 消息交换的复杂性时，WCF 服务模型通常是最佳选择开发的编程解决方案[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 但是，有些的方案中的 WCF 通道模型可能更好的选择;特别是在哪种流式处理方案非常重要。 这是因为序列化和反序列化的 XML 表示形式中的 SOAP 消息的对象和用来表示它们的服务模型中的.NET 类型之间涉及到读取到内存中的整个消息。 有关使用 WCF 通道模型的详细信息，请参阅[开发 SAP 应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)。
  
  在本部分中的主题包含信息、 步骤和示例来帮助你创建和使用 WCF 服务模型开发应用程序使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [使用 SAP 适配器的 WCF 服务模型概述](../../adapters-and-accelerators/adapter-sap/overview-of-the-wcf-service-model-with-the-sap-adapter.md)  
  
-   [元数据和具有 SAP 的 WCF 服务模型](../../adapters-and-accelerators/adapter-sap/metadata-and-the-wcf-service-model-with-sap.md)  
  
-   [生成 WCF 客户端或 WCF 服务约定的 SAP 解决方案项目](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)  
  
-   [为 SAP 系统配置客户端绑定](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md)  
  
-   [在 SAP 中的 Rfc 调用通过使用 WCF 服务模型](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-the-wcf-service-model.md)  
  
-   [使用 WCF 服务模型在 SAP 中接收入站的 RFC 调用](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-in-sap-using-the-wcf-service-model.md)  
  
-   [使用 WCF 服务模型调用 Trfc](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-the-wcf-service-model.md)  
  
-   [使用 WCF 服务模型在 SAP 中接收入站的 tRFC 调用](../../adapters-and-accelerators/adapter-sap/receive-inbound-trfc-calls-in-sap-using-the-wcf-service-model.md)  
  
-   [使用 WCF 服务模型调用在 SAP 中的 Bapi](../../adapters-and-accelerators/adapter-sap/invoke-bapis-in-sap-using-the-wcf-service-model.md)  
  
-   [通过使用 WCF 服务模型向 SAP 发送 Idoc](../../adapters-and-accelerators/adapter-sap/send-idocs-to-sap-using-the-wcf-service-model.md)