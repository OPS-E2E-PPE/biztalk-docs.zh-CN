---
title: 创建发送和接收端口 |Microsoft 文档
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
ms.openlocfilehash: da4b117ca2d032ef1dc10731128acca903a51790
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
ms.locfileid: "24014028"
---
# <a name="creating-send-and-receive-ports"></a>创建发送和接收端口
使用以下过程为用于 JD Edwards OneWorld 的 BizTalk 适配器创建 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 发送和接收端口。  
  
## <a name="creating-a-port"></a>创建端口  
  
#### <a name="to-create-a-send-port"></a>创建发送端口的步骤  
  
1.  单击**启动**，指向**所有程序**，指向**Microsoft BizTalk Server**，然后单击**BizTalk Server 管理**。  
  
2.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，然后展开**应用程序**，然后展开你想要创建发送端口的应用程序。  
  
3.  右键单击**发送端口**单击**新建**，然后单击**静态请求-响应端口**。  
  
4.  在**发送端口属性**对话框框中，执行以下操作：  
  
    -   在**名称**框中，键入发送端口名称 (例如， `SSOSendToJDE OneWorld`)。  
  
    -   从**类型**下拉列表中，选择**JDEdwards**。  
  
    -   从**发送处理程序**下拉列表中，选择发送处理程序地址。  
  
    -   有关**发送管道**，选择**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**。  
  
    -   有关**接收管道**，选择**Microsoft.BizTalk.DefaultPiplelines.XMLReceive**。  
  
5.  单击 **“确定”**。  
  
## <a name="creating-a-receive-port"></a>创建接收端口  
  
#### <a name="to-create-a-receive-port"></a>若要创建接收端口  
  
1.  单击**启动**，指向**所有程序**，指向**Microsoft BizTalk Server**，然后单击**BizTalk Server 管理**。  
  
2.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，然后展开**应用程序**，然后展开你想要创建发送端口的应用程序。  
  
3.  右键单击**接收端口**单击**新建**，然后单击**单向接收端口**。  
  
     上**单向接收端口属性**屏幕上，在**名称**字段中，键入`ReceiveFromHttp`，然后单击**确定**。  
  
4.  输入中的以下信息**单向接收端口属性**窗口：  
  
    -   在**名称**字段中，键入`ReceiveFromHTTP`。  
  
    -   有关**传输类型**，选择**HTTP**。  
  
5.  在地址 (URI) 中单击省略号 (…) 按钮。  
  
     ![](../core/media/siebeladapter-32-ssodemo-httptransport.gif "SiebelAdapter_32_SSODemo_HTTPTransport")  
  
    1.  设置虚拟目录和 ISAPI 扩展 /mySSODemo/BTSHTTPReceive.dll。  
  
    2.  选择**成功后返回的相关句柄**。  
  
    3.  选择**使用单一登录**，然后单击**确定**。  
  
6.  在**接收处理程序**下拉列表中，选择**BizTalkServerIsolatedHost**。  
  
     ![](../core/media/siebeladapter-33-ssodemo-receivelocationproperty.gif "SiebelAdapter_33_SSODemo_ReceiveLocationProperty")  
  
7.  有关**接收管道**，选择**Microsoft.BizTalk.DefaultPiplelines.XMLReceive**，然后单击**确定**。  
  
## <a name="see-also"></a>另请参阅  
 [将项目添加到 BizTalk 管理](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)   
 [将项目添加到 BizTalk 管理](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)   
 [适配器中的安全](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)