---
title: "为 Siebel eBusiness 应用程序的 BizTalk Adapter 概述 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- overview, adapter
- adapter, overview of
- adapter, overview
ms.assetid: 41ab7d42-7096-45ef-9763-a5ccf88eb652
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efcc3a90f7025a5f396cd778676f5f3152bc7657
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="overview-of-biztalk-adapter-for-siebel-ebusiness-applications"></a>为 Siebel eBusiness 应用程序的 BizTalk Adapter 概述
[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]公开 Siebel 系统作为 WCF 服务。 适配器客户端可以通过交换 SOAP 消息与适配器执行 Siebel 系统上的操作。 适配器使用 WCF 消息，并且到 Siebel 系统的适当调用来执行该操作。 适配器回客户端的 SOAP 消息的形式，并将响应返回从 Siebel 系统。  
  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]曲面 Siebel 项目 （业务服务中的业务组件） 的描述的元数据的结构的 SOAP 消息的 WSDL 形式。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]和[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]才能使适配器客户端检索操作的元数据并在编程解决方案中生成可用的编程项目。  
  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel COM 数据控件用于访问 Siebel 系统。 Siebel COM 数据控件与 Siebel Web 客户端捆绑。 因此，确保您具有相同的计算机上安装了 Siebel Web 客户端[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。 你可以使用[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]以下列方式与 Siebel 系统进行通信：  
  
-   通过开发 BizTalk 应用程序。 请参阅[开发 BizTalk Server 应用程序](../../core/developing-biztalk-server-applications.md)。
  
-   通过使用 WCF 服务模型。 请参阅[开发 Siebel 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md)。  
  
-   通过使用 WCF 通道模型。 请参阅开发 Oracle 数据库应用程序使用 WCF 通道模型[此处输入链接说明](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [适配器如何连接到 Siebel 系统？](https://msdn.microsoft.com/library/cc185212(v=bts.10).aspx)  
  
-   [原理适配器图面 Siebel 元数据是什么？](https://msdn.microsoft.com/library/cc185267(v=bts.10).aspx)  
  
-   [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)  
  
-   [适配器支持的其他功能](https://msdn.microsoft.com/library/cc185252(v=bts.10).aspx) 
  
## <a name="see-also"></a>另请参阅  
 [为 Siebel eBusiness 应用程序了解的 BizTalk Adapter](../../adapters-and-accelerators/adapter-siebel/understand-biztalk-adapter-for-siebel-ebusiness-applications.md)