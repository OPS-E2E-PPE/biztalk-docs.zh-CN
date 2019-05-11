---
title: 创建发送和接收端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- JD Edwards OneWorld adapters, receive ports
- adapters [JD Edwards OneWorld adapters], receive ports
- creating, receive ports [JD Edwards OneWorld adapters]
- send ports, creating [JD Edwards OneWorld adapters]
- adapters [JD Edwards OneWorld adapters], send ports
- adapters [JD Edwards OneWorld adapters], transport properties
- JD Edwards OneWorld adapters, send ports
- JD Edwards OneWorld adapters, transport properties
- receive ports, creating [JD Edwards OneWorld adapters]
- creating, send ports [JD Edwards OneWorld adapters]
ms.assetid: fb4ca8b1-40d9-4beb-a791-554086f8ca98
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 808c3d7295031832852ca40596a77a369aedb507
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353578"
---
# <a name="creating-send-and-receive-ports"></a>创建发送和接收端口
使用以下过程创建[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]发送和接收端口的 BizTalk 适配器用于 JD Edwards OneWorld。  
  
## <a name="creating-a-port"></a>创建端口  
  
#### <a name="to-create-a-send-port"></a>若要创建的发送端口  
  
1.  单击**启动**，依次指向**所有程序**，指向**Microsoft BizTalk Server**，然后单击**BizTalk Server 管理**。  
  
2.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，然后展开**应用程序**，然后展开要为其创建发送端口的应用程序。  
  
3.  右键单击**发送端口**然后单击**新建**，然后单击**静态要求响应端口**。  
  
4.  在中**发送端口属性**对话框框中，执行以下操作：  
  
    -   在中**名称**框中，键入发送端口名称 (例如， `SSOSendToJDE OneWorld`)。  
  
    -   从**类型**下拉列表中，选择**JDEdwards**。  
  
    -   从**发送处理程序**下拉列表中，选择发送处理程序地址。  
  
    -   有关**发送管道**，选择**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**。  
  
    -   有关**接收管道**，选择**Microsoft.BizTalk.DefaultPiplelines.XMLReceive**。  
  
5.  单击“确定” 。  
  
## <a name="creating-a-receive-port"></a>创建接收端口  
  
#### <a name="to-create-a-receive-port"></a>若要创建的接收端口  
  
1.  单击**启动**，依次指向**所有程序**，指向**Microsoft BizTalk Server**，然后单击**BizTalk Server 管理**。  
  
2.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，然后展开**应用程序**，然后展开要为其创建发送端口的应用程序。  
  
3.  右键单击**接收端口**然后单击**新建**，然后单击**单向接收端口**。  
  
     上**单向接收端口属性**屏幕上，在**名称**字段中，键入`ReceiveFromHttp`，然后单击**确定**。  
  
4.  输入中的以下信息**单向接收端口属性**窗口：  
  
    -   在中**名称**字段中，键入`ReceiveFromHTTP`。  
  
    -   有关**传输类型**，选择**HTTP**。  
  
5.  单击地址 (URI) 中的省略号 （...） 按钮。  
  
     ![](../core/media/siebeladapter-32-ssodemo-httptransport.gif "SiebelAdapter_32_SSODemo_HTTPTransport")  
  
    1.  设置虚拟目录和 ISAPI 扩展 /myssodemo/btshttpreceive.dll。  
  
    2.  选择**成功后的返回相关句柄**。  
  
    3.  选择**使用单一登录**，然后单击**确定**。  
  
6.  在中**接收处理程序**下拉列表中，选择**BizTalkServerIsolatedHost**。  
  
     ![](../core/media/siebeladapter-33-ssodemo-receivelocationproperty.gif "SiebelAdapter_33_SSODemo_ReceiveLocationProperty")  
  
7.  有关**接收管道**，选择**Microsoft.BizTalk.DefaultPiplelines.XMLReceive**，然后单击**确定**。  
  
## <a name="see-also"></a>请参阅  
 [将项目添加到 BizTalk 管理](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)   
 [将项目添加到 BizTalk 管理](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)   
 [适配器中的安全性](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)