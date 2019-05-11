---
title: 用于 Siebel eBusiness 应用程序的 BizTalk 适配器概述 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- overview, adapter
- adapter, overview of
- adapter, overview
ms.assetid: 41ab7d42-7096-45ef-9763-a5ccf88eb652
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16d62607a1c970b0d391a8077da4ddecb8d86160
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371288"
---
# <a name="overview-of-biztalk-adapter-for-siebel-ebusiness-applications"></a>用于 Siebel eBusiness 应用程序的 BizTalk 适配器概述
[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]公开为 WCF 服务的 Siebel 系统。 适配器客户端可以通过该适配器与交换的 SOAP 消息执行 Siebel 系统的操作。 适配器使用 WCF 消息，并执行到 Siebel 系统的相应调用以执行该操作。 适配器返回到 SOAP 消息的窗体中的客户端从 Siebel 系统返回的响应。  
  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]曲面的 Siebel 项目 （业务组件、 业务服务） 描述的元数据结构的 SOAP 消息的 WSDL 格式。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]和[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]启用适配器客户端来检索操作的元数据，并在生成的编程项目，可以使用编程解决方案中。  
  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]使用 Siebel COM 数据控件访问 Siebel 系统。 Siebel COM 数据控件捆绑了 Siebel Web 客户端。 因此，请确保已安装在同一台计算机上的 Siebel Web 客户端[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。 可以使用[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]以以下方式与 Siebel 系统进行通信：  
  
-   通过开发 BizTalk 应用程序。 请参阅[开发 BizTalk Server 应用程序](../../core/developing-biztalk-server-applications.md)。
  
-   通过使用 WCF 服务模型。 请参阅[开发 Siebel 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md)。  
  
-   通过使用 WCF 通道模型。 请参阅开发 Oracle 数据库应用程序使用 WCF 通道模型[此处输入链接说明](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [适配器如何连接到 Siebel 系统？](https://msdn.microsoft.com/library/cc185212(v=bts.10).aspx)  
  
-   [原理适配器图面上的 Siebel 元数据是什么？](https://msdn.microsoft.com/library/cc185267(v=bts.10).aspx)  
  
-   [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)  
  
-   [适配器支持的其他功能](https://msdn.microsoft.com/library/cc185252(v=bts.10).aspx) 
  
## <a name="see-also"></a>请参阅  
 [了解用于 Siebel eBusiness 应用程序的 BizTalk 适配器](../../adapters-and-accelerators/adapter-siebel/understand-biztalk-adapter-for-siebel-ebusiness-applications.md)