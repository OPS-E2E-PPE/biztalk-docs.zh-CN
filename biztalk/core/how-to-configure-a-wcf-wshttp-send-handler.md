---
title: 如何配置 Wcf-wshttp 发送处理程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-WSHttp adapters, global variables
- configuring [WCF-WSHttp adapters], send handlers
- configuring [WCF-WSHttp adapters], global variables
- send handlers, WCF-WSHttp adapters
ms.assetid: b2c30edb-8f7b-4d3c-812b-5b877c47fda1
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fe3ba5d5338403b5ebfa0796ca4a31963e251d6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014750"
---
# <a name="how-to-configure-a-wcf-wshttp-send-handler"></a>如何配置 WCF-WSHttp 发送处理程序
使用以下过程可配置 WCF-WSHttp 发送处理程序。  

> [!CAUTION]
>  使用 WCF-WSHttp 适配器处理程序时，建议在 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] 或 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 计算机上安装这些处理程序的主机实例。  

### <a name="to-change-global-variables-for-a-wcf-wshttp-send-handler"></a>更改 WCF-WSHttp 发送处理程序的全局变量  

1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**平台设置**，然后展开**适配器**。  

2. 在展开的适配器列表中，单击**Wcf-wshttp**，在右窗格中，右键单击你想要配置，发送处理程序，再单击**属性**。  

3. 在中**适配器处理程序属性**对话框中，在**常规**选项卡上，在**主机名**列表中，选择接收处理程序将关联的主机。  

4. 在中**常规**选项卡上，单击**属性**，然后在**代理**选项卡上，执行以下操作。  


   |   使用此选项    |                                                                                                                                                                                                                        执行的操作                                                                                                                                                                                                                        |
   |---------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **使用代理** |                                                                                                                                                                              指示此发送端口是否使用代理服务器。<br /><br /> 默认值为清除此复选框。                                                                                                                                                                              |
   |  **Address**  |                      指定代理服务器的地址。 使用**https**或**http**具体取决于安全配置的方案。 此地址后面可跟冒号和端口号。 例如， http://127.0.0.1:8080。<br /><br /> 此属性需要值才**使用代理**处于选中状态。<br /><br /> 类型：字符串<br /><br /> 最大长度：256<br /><br /> 默认值为空字符串。                      |
   | **用户名** | 指定用于身份验证的用户名。 如果使用集成或基本验证，则用户名将包括域，即采用“域\用户名”格式。 如果使用摘要式身份验证，则用户名不包括域\\。<br /><br /> 此属性需要值才**使用代理**处于选中状态。<br /><br /> 类型：字符串<br /><br /> 最小长度：0<br /><br /> 最大长度：256<br /><br /> 默认值为空字符串。 |
   | **密码**  |                                                                                             指定用于身份验证的密码。<br /><br /> 此属性需要值才**使用代理**处于选中状态。<br /><br /> 类型：字符串<br /><br /> 最小长度：0<br /><br /> 最大长度：256<br /><br /> 默认值为空字符串。                                                                                             |


5. 单击“确定” 。  

## <a name="see-also"></a>请参阅  
 [配置 WCF-WSHttp 适配器](../core/configuring-the-wcf-wshttp-adapter.md)