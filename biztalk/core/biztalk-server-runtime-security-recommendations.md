---
title: BizTalk Server 运行时安全建议 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, runtime
- runtime, security
- discretionary access control lists (DACLs)
- DACLs
- .NET Framework Code Access Security Mechanism
ms.assetid: 1933789d-b79a-47ad-8f70-6f1e99bc2be0
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27386b7294294088b7dcfcad1198e410e56e724d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232229"
---
# <a name="biztalk-server-runtime-security-recommendations"></a>BizTalk Server 运行时安全建议
必须在用来接收、发送、处理和跟踪消息的所有计算机上安装 BizTalk Server 运行时或引擎。 换句话说，必须在创建 BizTalk 主机实例（处理服务器）的所有计算机上安装运行时组件。 建议您遵循以下准则以确保您的环境中的 BizTalk Server 运行时的安全并对其进行部署：  
  
-   确保使用最低的安全用户权限来执行 BizTalk 运行时任务。 有关最低安全用户权限的详细信息，请参阅[最低安全用户权限](../core/minimum-security-user-rights.md)。  
  
    > [!NOTE]
    >  BizTalk 配置会为帐户授予执行其任务所需的最低权限。  
  
-   各个主机实例的服务帐户必须对运行该主机实例的计算机具有“作为服务登录”权限。  
  
-   只有主机的服务帐户才有权访问与主机相关的 MessageBox 数据，并且只有这些服务才能向 MessageBox 发布数据。 为了最大限度地减少信息泄露攻击的潜在可能性，不应为多个主机使用同一服务帐户。  
  
-   处理服务器（不承载跟踪任务的主机）只需连接到 MessageBox 和管理数据库以及主密钥服务器。 如果使用 Internet 协议安全性 (IPSec)，则可以将处理服务器限定为只能访问这两个数据库和主密钥服务器。  
  
-   在同一 BizTalk 主机中运行的所有组件都具有与该主机相同的信任级别。 至于哪些组件应在同一主机下运行从而共享同一信任级别，这需要由 BizTalk 管理员来决定。 BizTalk 确保在 BizTalk 主机中只运行 BizTalk 管理员安装的程序集。 若要进一步限制 BizTalk 可使用的程序集（例如，若要将 BizTalk 限制为只能运行特定供应商签署的程序集）或验证业务流程的强名称签名，可以使用 [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] 代码访问安全机制。 有关 Microsoft MSDN 网站在详细信息[http://go.microsoft.com/fwlink/?LinkId=60947](http://go.microsoft.com/fwlink/?LinkId=60947)。  
  
-   发布消息的授权粒度处于 BizTalk 主机级别上。 换句话说，如果在同一 BizTalk 主机中运行有多个业务流程或适配器，则无法限制为由某个特定的业务流程来接收发送到该主机的消息。  
  
-   如果主机未获得接收消息的授权，则该主机将把消息放在其挂起队列中。 默认情况下，如果接收适配器和业务流程运行在同一主机中，则业务流程可以读取主机的挂起队列。 这样，业务流程就可以提取由于授权失败而被 BizTalk 挂起的消息。 因此，建议不要在同一主机中运行业务流程和接收适配器。  
  
-   主机实例是在特定计算机中运行的 Windows 服务。 若要创建主机实例，您必须为要在其中创建主机实例的计算机的 BizTalk 管理员和 Windows 管理员，因为 BizTalk 需要创建与主机实例对应的 Windows 服务。  
  
-   当 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 生成程序集时，它会使用集成开发人员环境 (IDE) 生成的自定义密钥。 如果你的环境需要使用特定密钥进行签名的所有程序集，你必须配置适用于所有开发计算机的 IDE，使用该密钥或使用延迟签名的程序集...  
  
-   接收和发送管道中的所有组件都会试图保持较低的内存占用率。 当数据大于特定阈值时，这些组件会将数据保存到磁盘上的临时文件夹 (%TEMP%) 中。 必须确保主机实例的服务帐户的临时文件夹具有正确的任意访问控制列表 (DACL)，以便只有该服务帐户才能读取这些文件。 还必须确保临时文件夹具有足够的空间来存储可能的大型文件。  
  
## <a name="see-also"></a>另请参阅  
 [管理 BizTalk Server 安全性](../core/managing-biztalk-server-security.md)   
 [处理服务器的端口](../core/ports-for-the-processing-servers.md)   
 [BizTalk Server 部署的安全建议](../core/security-recommendations-for-a-biztalk-server-deployment.md)   
 [Planning for Security](../core/planning-for-security.md)