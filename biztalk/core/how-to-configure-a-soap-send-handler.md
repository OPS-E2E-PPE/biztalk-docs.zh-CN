---
title: "如何配置 SOAP 发送处理程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send handlers, SOAP adapters
- SOAP adapters, denial of service
- denital of service, HTTP adapters
- configuring [SOAP adapters], send handlers
- configuring [SOAP adapters], denial of service
- SOAP adapters, send handlers
- denial of service, SOAP adapters
ms.assetid: fd610a3f-ca10-42e0-b81e-219e07e33830
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65ca116b47e36d754b27839a09225aeb313c9e0f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-a-soap-send-handler"></a>如何配置 SOAP 发送处理程序
使用以下过程可配置 SOAP 发送处理程序。  
  
> [!CAUTION]
>  在使用 HTTP 或 SOAP 适配器处理程序，建议你在 Microsoft 上安装这些处理程序的主机实例[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]或[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]计算机。  
  
### <a name="to-change-global-variables-for-a-soap-send-handler"></a>更改 SOAP 发送处理程序的全局变量  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**平台设置**，然后展开**适配器**。  
  
2.  在展开的适配器列表中，单击**SOAP**，而是在右窗格中，右键单击你想要配置，则发送处理程序，然后单击**属性**。  
  
3.  在**适配器处理程序属性**对话框中，在**常规**选项卡上，在**主机名**列表中，选择接收处理程序将与之关联的主机。  
  
4.  上**代理**选项卡上，执行以下操作。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**使用代理**|表示 SOAP 发送处理程序是否使用代理服务器。|  
    |**Server**|指定代理服务器的名称。<br /><br /> 此属性仅需要一个值，如果**使用代理**选择。<br /><br /> 类型：字符串<br /><br /> 最小长度：0<br /><br /> 最大长度：256|  
    |**端口**|指定 SOAP 发送处理程序使用的端口。<br /><br /> 此属性仅需要一个值，如果**使用代理**选择。<br /><br /> 默认值：80<br /><br /> 类型： 长<br /><br /> 最小值： 0<br /><br /> 最大值： 65535|  
    |**用户名**|指定用于身份验证的用户名。<br /><br /> 此属性仅需要一个值，如果**使用代理**选择。<br /><br /> 类型：字符串<br /><br /> 最小长度：0<br /><br /> 最大长度：256|  
    |**密码**|指定用于身份验证的密码。<br /><br /> 此属性仅需要一个值，如果**使用代理**选择。<br /><br /> 类型：字符串<br /><br /> 最小长度：0<br /><br /> 最大长度：256|  
  
5.  单击 **“确定”**。  
  
## <a name="see-also"></a>另请参阅  
 [配置 SOAP 适配器](../core/configuring-the-soap-adapter.md)   
 [发布 Web 服务](../core/publishing-web-services.md)