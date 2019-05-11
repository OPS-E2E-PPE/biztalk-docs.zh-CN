---
title: 路线接入点 Web 服务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d7551974-b9d2-4ae3-b54c-3aa5ba058e95
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a23c12726915a4f84f8c33ff4a984e5e9aae4fe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399759"
---
# <a name="the-itinerary-on-ramp-web-services"></a>路线接入点 Web 服务
路线 Web 服务是路线接入点公开的方法，允许客户端将消息提交以处理由路线服务，然后迁移到目标 Microsoft BizTalk 或 ESB 操作。  
  
 该路线 Web 服务通过有效负载到 ESB 路线管道组件中，验证路线以便验证是否在定义了这些服务[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]配置。 然后组件将特殊的上下文属性添加到包含已验证的旅行计划的消息。  
  
 对于泛型路线接入点，在提交消息期间未提供包含路线的 SOAP 标头。 相应地，ESB 路线选择器管道组件将代替 ESB 路线管道组件。 ESB 路线选择器管道组件解决了基于预定义冲突解决程序的连接字符串，路线，并提供相同 ESB 路线管道组件提供的验证。  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包括两种变体的路线服务，以支持这两个单向和请求-响应消息交换模式。 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包含 ASP.NET (ASMX) 和 Windows Communication Foundation (WCF) 版本的这两种服务，并提供了泛型版本的 WCF 服务。  
  
 提供的单向路线服务的名称是**ESB。ItineraryService**， **ESB。ItineraryServices.WCF**，和**ESB。ItineraryServices.Generic.WCF**。  
  
 提供双向路线服务的名称是**ESB。ItineraryServices.Response**， **ESB。ItineraryServices.Response.WCF**，和**ESB。ItineraryServices.Generic.Response.WCF**。  
  
 每个路线 Web 服务公开以下方法：  
  
- **SubmitRequest**。 对于基于 ASMX 的服务，此方法采用的实例**XmlNode**类，该类包含要提交的邮件。 对于基于 WCF 的服务，此方法采用一个 XML 字符串，包含要提交的邮件。  
  
- **SubmitRequestResponse**。 对于基于 ASMX 的服务，此方法将引用的实例**XmlNode**类，该类包含要提交的消息并返回响应消息中的实例**XmlNode**传递给它。 对于基于 WCF 的服务，此方法将引用**对象**类型，它是一个 XML 字符串，包含要提交的消息，并返回一个数组**XmlNodes**中**对象**传递给它。  
  
  有关使用路线 Web 服务的详细信息，请参阅[安装和运行路线接入点示例](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)。  
  
> [!NOTE]
>  默认情况下，路线 Web 服务未配置为需要安全套接字层 (SSL) 客户端进行访问时。 您应要求将 SSL 用于客户端访问和保护 Internet 信息服务 (IIS) Web 服务主机计算机和承载使用网络级别 IPSec ESBExceptions 数据库的服务器之间的连接和相应的服务配置文件级访问控制列表 (ACL) 权限。