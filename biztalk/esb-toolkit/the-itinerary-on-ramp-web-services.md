---
title: "路线上负载增加 Web 服务 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d7551974-b9d2-4ae3-b54c-3aa5ba058e95
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36d3724a6cd57dca8157c05e95d9e196f0fb6cf8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-itinerary-on-ramp-web-services"></a>路线上负载增加 Web 服务
路线 Web 服务是路线入口公开一个方法，以便客户端提交处理路线服务，然后迁移到目标 Microsoft BizTalk 或 ESB 操作的消息。  
  
 路线 Web 服务将传递负载给 ESB 路线管道组件中，验证路线后，若要验证是否在定义了这些服务[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]配置。 然后组件将特殊的上下文属性添加到包含已验证的路线的消息。  
  
 对于泛型路线上的负载增加，包含一条路线的 SOAP 标头在未提供消息提交过程。 相应地，ESB 路线选择器管道组件代替 ESB 路线管道组件。 ESB 路线选择器管道组件解析路线基于预定义的解析程序连接字符串，并提供所 ESB 路线管道组件提供的相同验证。  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包括两种变体的路线服务以支持这两个单向和请求-响应消息交换模式。 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包含 ASP.NET (ASMX) 和 Windows Communication Foundation (WCF) 版本的这两种服务，并且它提供泛型版本的 WCF 服务。  
  
 提供的单向路线服务的名称是**ESB。ItineraryService**， **ESB。ItineraryServices.WCF**，和**ESB。ItineraryServices.Generic.WCF**。  
  
 提供的双向路线服务的名称是**ESB。ItineraryServices.Response**， **ESB。ItineraryServices.Response.WCF**，和**ESB。ItineraryServices.Generic.Response.WCF**。  
  
 每个路线 Web 服务公开以下方法：  
  
-   **SubmitRequest**。 对于基于 ASMX 的服务中，此方法采用实例**XmlNode**包含要提交的消息的类。 对于基于 WCF 的服务中，此方法采用包含要提交的消息的 XML 字符串。  
  
-   **SubmitRequestResponse**。 对于基于 ASMX 的服务中，此方法采用指向的实例的引用**XmlNode**类，该类包含要提交的消息并将返回响应消息的实例中**XmlNode**传递给它。 对于基于 WCF 的服务中，此方法会引用**对象**XML 字符串，包含要提交的消息，并返回的数组的类型**XmlNodes**中**对象** ，已传递给它。  
  
 有关使用路线 Web 服务的详细信息，请参阅[安装和运行路线上负载增加示例](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)。  
  
> [!NOTE]
>  默认情况下，路线 Web 服务未配置为要求安全套接字层 (SSL) 时的客户端访问。 您应将要求将 SSL 用于客户端访问和保护 Internet Information Services (IIS) Web 服务主机计算机和承载使用网络级别 IPSec ESBExceptions 数据库的服务器之间的连接并适当的服务配置文件级访问控制列表 (ACL) 权限。