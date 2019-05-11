---
title: 如何配置 HTTP 发送处理程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send handlers, HTTP adapters
- configuring [HTTP adapters], send handlers
- HTTP adapters, send handlers
ms.assetid: 821bf30c-b220-4ded-953d-7e745c0698b9
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 53da31eba06cb5b53ca18e7ddacafc75dda5ed55
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386417"
---
# <a name="how-to-configure-an-http-send-handler"></a>如何配置 HTTP 发送处理程序
使用以下过程来更改 HTTP 发送处理程序与之关联的主机。  

> [!NOTE]
>  每个主机可以只有一个与其关联的发送处理程序。  
> 
> [!CAUTION]
>  在使用 HTTP 或 SOAP 适配器处理程序，建议在 Microsoft 上安装这些处理程序的主机实例[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]，[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]计算机。  

### <a name="to-change-global-variables-for-an-http-send-handler"></a>若要更改全局变量为 HTTP 发送处理程序  

1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**平台设置**，然后展开**适配器**。  

2. 在展开的适配器列表中，单击**HTTP**，在右窗格中右键单击你想要配置，发送处理程序然后单击**属性**。  

3. 在中**适配器处理程序属性**对话框中，在**常规**选项卡上，在**主机名**列表中，选择发送处理程序将关联的主机。  

4. 上**属性**选项卡上，执行以下操作。  


   |         使用此选项          |                                                                                                                                                                                                 执行的操作                                                                                                                                                                                                  |
   |---------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **请求超时 （秒）** | 以秒为单位指定超时值时等待来自服务器的响应。<br /><br /> 如果设置为零 (0)，HTTP 适配器计算超时值根据请求消息的大小。<br /><br /> 如果未提供一个值，使用处理程序的值。<br /><br /> **默认值：** 0<br /><br /> **类型：** Long<br /><br /> **最小值：** 0<br /><br /> **最大值：** MAX_LONG |
   |   **最大重定向**   |                                                                                                       指定发送的消息所允许的最大重定向。<br /><br /> **默认值：** 5<br /><br /> **类型：** smallint<br /><br /> **最小值：** 0<br /><br /> **最大值：** 10                                                                                                       |
   |     **内容类型**      |                                                                 指定请求消息的内容类型。<br /><br /> 如果未提供一个值，使用处理程序的值。<br /><br /> **默认值：** Text/XML<br /><br /> **类型：** String<br /><br /> **最小长度：** 0<br /><br /> **最大长度：** 256                                                                  |


5. 上**代理**选项卡上，执行以下操作。  


   |   使用此选项    |                                                                                                                          执行的操作                                                                                                                           |
   |---------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **使用代理** |                                                                指定是否 HTTP 发送处理程序使用代理服务器。<br /><br /> **默认值：** False<br /><br /> **类型：** Boolean                                                                |
   |  **Server**   |               指定此发送端口的代理服务器地址。<br /><br /> 此属性需要一个值，如果**使用代理**是**True**。<br /><br /> **类型：** String<br /><br /> **最小长度：** 0<br /><br /> **最大长度：** 256                |
   |   **端口**    | 指定此发送端口的代理服务器端口。<br /><br /> 此属性需要一个值，如果**使用代理**是**True**。<br /><br /> **默认值：** 80<br /><br /> **类型：** Long<br /><br /> **最小值：** 0<br /><br /> **最大值：** 65535 |
   | **用户名** |      指定要使用代理服务器进行身份验证的用户名称。<br /><br /> 此属性需要一个值，如果**使用代理**是**True**。<br /><br /> **类型：** String<br /><br /> **最小长度：** 0<br /><br /> **最大长度：** 256       |
   | **密码**  |        指定代理服务器进行身份验证的用户密码。<br /><br /> 此属性需要一个值，如果**使用代理**是**True**。<br /><br /> **类型：** String<br /><br /> **最小长度：** 0<br /><br /> **最大长度：** 256        |


6. 单击“确定” 。  

## <a name="see-also"></a>请参阅  
 [配置 HTTP 适配器](../core/configuring-the-http-adapter.md)