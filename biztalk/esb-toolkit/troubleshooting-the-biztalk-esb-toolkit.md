---
title: 故障排除 BizTalk ESB 工具包 |Microsoft 文档
description: 解决安装问题，以及与 BizTalk Server 中 ESB 工具包的常见错误
caps.latest.revision: 2
author: MandiOhlinger
manager: anneta
ms.custom: ''
ms.date: 08/10/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e1ea2d56-2ace-40f2-80df-8a7489bbfc2e
ms.author: mandia
ms.openlocfilehash: 8fc1305e481de2444a54ea994f8a53da83b2eaed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295341"
---
# <a name="troubleshoot-the-biztalk-esb-toolkit"></a>解决 BizTalk ESB 工具包

  
## <a name="installation"></a>安装  
  
|问题|解决方法|  
|-----------|----------------|  
|收到安装期间出现"分配权限的错误"的异常。|[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]使用标准的 BizTalk 帐户组，必须存在在安装过程中或安装将失败。 此外，该工具包假设其中的计算机是工作组的成员的独立安装或安装企业版的计算机所在域的成员。|  
|应用程序导入失败并显示错误消息，警告的信任级别不匹配。|Microsoft.BizTalk.ESB 绑定文件被配置为使用默认值，BizTalkServerApplication 和 BizTalkServerIsolatedHost，反过来配置为在不受信任模式下执行。 如果你已更改你的主机在受信任模式下运行，将不导入绑定文件。 若要纠正此问题，你必须将信任级别更改为不受信任或编辑以满足你的环境中的 BizTalk 工具包 \Bindings 目录的绑定文件。|  
|Kerberos 身份验证未配置 Internet 信息服务 (IIS) 中。|若要启用 Kerberos 身份验证的 IIS，请参阅 Microsoft 知识库中的以下文章：<br /><br /> -   [如何配置 IIS 以支持 Kerberos 协议和 NTLM 协议的网络身份验证](http://go.microsoft.com/fwlink/?LinkId=188566)<br />-   [如何启用 IIS 以在不是域控制器的计算机上使用 Kerberos 身份验证](http://go.microsoft.com/fwlink/?LinkId=188567)<br />-   [你不能为 Internet 信息服务 (IIS) 7.0 为 Windows 集成身份验证在 IIS 管理器中配置 Negotiate 或 NTLM 协议](http://go.microsoft.com/fwlink/?LinkId=188568)|  
  
## <a name="general-issues"></a>一般问题  
  
|问题|解决方法|  
|-----------|----------------|  
|向通用 ESB 路线上负载增加 Web 服务发送一条消息时，你会收到"内部 SOAP 处理"异常。|使用 BizTalk Server 管理控制台来确保 Microsoft.Practices.ESB 应用程序正在运行;如果未运行，，启动它。|  
|在管理门户中 ESB 站点中不显示异常消息。|检查 BizTalk 管理员组概述页和 Windows 应用程序事件日志，以指示失败发送消息的条目。 你可能需要重新配置异常发送适配器 （Microsoft.Practices.ESB 应用程序的一部分） 以匹配你的环境。 此外，请注意 BizTalk 失败消息路由功能和 BizTalk ESB 工具包异常管理框架生成的异常消息。 因此，请确保你启用**失败消息的路由**选项用于发送和接收端口。|  
|在使用静态的解析程序使用 WCF 服务，你将收到无效的 SOAP 操作异常。|如果 WCF 服务 SOAP 操作不包括的目标命名空间，采用以下格式设置的冲突解决程序中设置的 SOAP 操作值: {action} 以指示 ESB 工具包核心引擎在运行时将不连接的目标命名空间。|