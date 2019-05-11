---
title: 异常处理 Web 服务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dfe6ebdf-9b92-40c7-93fb-afd6c5f68aaa
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 924a8262c3ebe474f79c2c169f3fd58ed5e9e4fe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399735"
---
# <a name="the-exception-handling-web-service"></a>异常处理 Web 服务
异常处理 Web 服务接受的错误消息，并将其发布到 ESB 异常门户。 客户端应用程序可以创建异常消息，并将其提交到 ESB，其中为该异常类型或泛型处理程序中，配置任何处理程序可以处理该异常。 此服务的主要好处是它允许参与 ESB 异常处理机制的 ESB 应用程序以外的实体。  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包含此服务的两个版本： ASP.NET (ASMX) 版本和 Windows Communication Foundation (WCF) 版本。 服务名称是**ESB。ExceptionHandlingServices**和**ESB。ExceptionHandlingServices.WCF**分别和服务公开一个方法：  
  
- **SubmitFault**。 此方法采用的实例**FaultMessage**类，并没有返回值。  
  
  异常处理机制的工作方式的信息，请参阅[使用 ESB 异常管理](../esb-toolkit/using-esb-exception-management.md)。  
  
> [!NOTE]
>  默认情况下，异常处理 Web 服务未配置为需要安全套接字层 (SSL) 客户端进行访问时。 应配置服务，因此它需要 SSL 客户端访问和保护 Internet 信息服务 (IIS) Web 服务主机计算机和承载的服务器之间的连接**ESBExceptions**数据库使用网络级别 IPSec 和相应的文件级访问控制列表 (ACL) 权限。