---
title: BizTalk Server 运行时安全建议 |Microsoft Docs
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
ms.openlocfilehash: b1e452a7cf78f63ac128064620db3084e91946fe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357873"
---
# <a name="biztalk-server-runtime-security-recommendations"></a>BizTalk Server 运行时安全建议
必须在你想要接收、 发送、 处理和跟踪消息的所有计算机上安装 BizTalk Server 运行时或引擎。 换而言之，你必须在其中创建 BizTalk 主机实例 （处理服务器） 的任何计算机上安装运行的时组件。 建议您遵循这些准则以保护和部署你的环境中的 BizTalk Server 运行时。  
  
- 确保具有最低安全用户权限来执行 BizTalk 运行时任务。 有关最低安全用户权限的详细信息，请参阅[最低安全用户权限](../core/minimum-security-user-rights.md)。  
  
  > [!NOTE]
  >  BizTalk 配置会为帐户授予执行其任务所需的最低权限。  
  
- 每个主机实例的服务帐户必须具有日志作为服务运行该主机实例的计算机上的权限。  
  
- 仅在主机的服务帐户有权访问与主机相关的 MessageBox 数据，只有这些服务可以发布到 MessageBox。 为了尽量减少信息泄露攻击的可能性，您不应为多个主机使用相同的服务帐户。  
  
- 处理服务器 （不承载跟踪的主机） 只需连接到 MessageBox 和管理数据库和主密钥服务器。 如果使用 Internet 协议安全 (IPSec)，可以限制到这两个数据库的处理服务器与主密钥服务器的访问权限。  
  
- 相同的 BizTalk 主机中运行的所有组件都具有与主机相同的信任级别。 它是信任的由 BizTalk 管理员，以确定哪些组件应在同一主机下运行，因此，共享相同级别。 BizTalk 可确保只有 BizTalk 管理员安装的程序集运行 BizTalk 主机中。 如果你想要进一步限制 BizTalk 可使用的例如，如果你想要将 BizTalk 仅运行特定供应商签署的程序集或验证业务流程的强名称签名限制为可以使用[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]代码访问安全机制。 有关 Microsoft MSDN 网站上的详细信息[ http://go.microsoft.com/fwlink/?LinkId=60947 ](http://go.microsoft.com/fwlink/?LinkId=60947)。  
  
- 发布消息的授权粒度处于 BizTalk 主机级别。 换而言之，如果有多个业务流程或适配器相同的 BizTalk 主机中运行，你不能限制一个特定的业务流程接收消息发送到主机。  
  
- 当主机无权收到一条消息时，主机会将消息放置在其挂起队列。 默认情况下，如果接收适配器和在同一主机中运行业务流程、 业务流程可以读取主机的挂起的队列。 这样，它将使业务流程可以提取由于授权失败而被 BizTalk 挂起的消息。 因此，建议不运行业务流程和接收适配器在同一主机中。  
  
- 主机实例是特定计算机上运行的 Windows 服务。 若要创建的主机实例，您必须是 BizTalk 管理员并且想要创建该主机实例，因为 BizTalk 需要创建要与该主机实例相对应的 Windows 服务的计算机上的 Windows 管理员。  
  
- 当 Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]生成一个程序集，它使用的集成开发环境 (IDE) 生成的自定义密钥。 如果你的环境需要使用特定密钥进行签名的所有程序集，你必须配置为所有开发计算机 IDE 使用该密钥，或者使用延迟签名的程序集...  
  
- 接收和发送管道中的所有组件都尝试保持较低的内存占用量。 数据大小超过特定阈值时，这些组件流式传输到磁盘的临时文件夹 （%TEMP%) 中的数据。 必须确保主机实例的服务帐户的临时文件夹具有正确的任意访问控制列表 (Dacl)，以便只有该服务帐户可以读取这些文件。 你还必须确保临时文件夹具有足够的空间来存储可能很大的文件。  
  
## <a name="see-also"></a>请参阅  
 [管理 BizTalk Server 安全性](../core/managing-biztalk-server-security.md)   
 [用于处理服务器的端口](../core/ports-for-the-processing-servers.md)   
 [BizTalk Server 部署的安全建议](../core/security-recommendations-for-a-biztalk-server-deployment.md)   
 [规划安全性](../core/planning-for-security.md)