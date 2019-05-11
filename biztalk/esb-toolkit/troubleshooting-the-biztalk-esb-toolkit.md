---
title: BizTalk ESB 工具包疑难解答 |Microsoft Docs
description: 排查安装问题，并与 ESB 工具包在 BizTalk Server 中的常见错误
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
ms.openlocfilehash: 11c673b2bbfde82a29acc94378d4b26f1d721da0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399598"
---
# <a name="troubleshoot-the-biztalk-esb-toolkit"></a>BizTalk ESB 工具包疑难解答

  
## <a name="installation"></a>安装  
  
|                                       问题                                        |                                                                                                                                                                                                                                                                                                                            解决方法                                                                                                                                                                                                                                                                                                                            |
|------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    您收到在安装过程中的"分配权限时出错"异常。     |                                                                                                                                           [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]使用标准的 BizTalk 帐户组，必须存在于安装过程中或在安装将失败。 此外，该工具包假定计算机的工作组的成员的位置的独立安装或企业安装计算机所在域的成员。                                                                                                                                           |
| 应用程序导入失败并显示错误消息，警告的信任级别不匹配。 |                                                                                                  Microsoft.BizTalk.ESB 绑定文件配置为使用默认值，BizTalkServerApplication 和 BizTalkServerIsolatedHost，进而配置为在不受信任模式下执行。 如果已更改你的主机在受信任模式下运行，不会导入绑定文件。 若要更正此问题，必须更改为不受信任的信任级别或编辑绑定文件，以适合您的环境中 BizTalk 工具包 \Bindings 目录。                                                                                                   |
| 在 Internet 信息服务 (IIS) 未配置 Kerberos 身份验证。  | 若要启用 IIS 的 Kerberos 身份验证，请参阅 Microsoft 知识库中的以下文章：<br /><br /> -   [如何配置 IIS 以用于网络身份验证支持 Kerberos 协议和 NTLM 协议](http://go.microsoft.com/fwlink/?LinkId=188566)<br />-   [如何使 IIS 能够在不是域控制器的计算机上使用 Kerberos 身份验证](http://go.microsoft.com/fwlink/?LinkId=188567)<br />-   [你无法为 Internet 信息服务 (IIS) 7.0 的 Windows 集成身份验证在 IIS 管理器中配置 Negotiate 或 NTLM 协议](http://go.microsoft.com/fwlink/?LinkId=188568) |
  
## <a name="general-issues"></a>一般问题  
  
|问题|解决方法|  
|-----------|----------------|  
|将消息发送到通用的 ESB 路线接入点 Web 服务时收到"内部 SOAP 处理"异常。|使用 BizTalk Server 管理控制台来确保 Microsoft.Practices.ESB 应用程序正在运行;如果未运行，，启动它。|  
|ESB 管理门户站点中未出现异常消息。|检查 BizTalk 管理员组概述页和 Windows 应用程序事件日志以指示发送消息的失败的条目。 您可能需要重新配置异常发送适配器 （Microsoft.Practices.ESB 应用程序的一部分） 以匹配你的环境。 此外，请注意，BizTalk 失败消息路由功能和 BizTalk ESB 工具包异常管理框架生成的异常消息。 因此，请确保您启用**失败消息路由**选项用于发送和接收端口。|  
|当与静态解析程序使用 WCF 服务，将收到无效的 SOAP 操作异常。|如果 WCF 服务的 SOAP 操作不包括的目标命名空间，采用以下格式设置的冲突解决程序中设置的 SOAP 操作值: {action} 以指示不通过 ESB 工具包核心引擎在运行时要连接的目标命名空间。|