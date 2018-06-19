---
title: 步骤 2： 配置双向的 WCF WebHttp 发送端口 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0bcab296-7921-4df4-abcc-eea78cc827e8
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f355275f9480cfa13f3a15bcc6522fbe7ec83b8c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278885"
---
# <a name="step-2-configure-a-two-way-wcf-webhttp-send-port"></a>步骤 2： 配置双向的 WCF WebHttp 发送端口
在此步骤中你配置的双向**WCF WebHttp**发送端口来调用 REST 资源 URL，以检索在美国无线运营商的计划中的延迟。  
  
### <a name="to-configure-wcf-webhttp-send-port"></a>配置 WCF-WebHttp 发送端口的步骤  
  
1.  从 BizTalk Server 管理控制台，在**BizTalk 应用程序 1**节点，右键单击**发送端口**，指向**新建**，然后单击**静态请求作出响应发送端口**。  
  
2.  在 **“常规”** 选项卡上，请执行下列操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**名称**|类型**SendPortRESTAzureMarketPlace**。|  
    |**类型**|选择**WCF WebHttp**。|  
    |**发送处理程序**|选择“BizTalkServerApplication” 。|  
    |**发送管道**|选择**PassThruTransmit**。|  
    |**接收管道**|选择**PassThruReceive**。|  
  
     单击**配置**。  
  
3.  从**WCF WebHttp 传输属性**对话框框中，执行以下操作：  
  
    1.  上**常规**选项卡上，为**地址 (URI)**，输入`https://api.datamarket.azure.com/oakleaf/US_Air_Carrier_Flight_Delays_Incr/`。  
  
    2.  在常规选项卡上，为**HTTP 方法和 URL 映射**，请输入以下命令：  
  
        ```  
        <BtsHttpUrlMapping>  
        <Operation Method="GET" Url="/On_Time_Performance" />  
        </BtsHttpUrlMapping>  
  
        ```  
  
         在这里，**获取**是 HTTP 动词和**On_Time_Performance**追加到要构造一个唯一的资源 URL 以检索航班延迟的基 URI。  
         
         > [!TIP] 
         > 在 URL 字段中，任何特殊的 XML 字符必须是"转义"。 这将确保特殊 XML 字符是处理，并通过端口保留。 例如，`&`必须作为转义特殊字符`&amp;`。 
           >
           >从：`Url=”/Customer?{ID}& group=Location”`
           >
           >
           >自：`Url=”/Customer?{ID}&amp;group=Location”`
  
    3.  上**绑定**选项卡上，为**最大接收消息大小**字段中，选择一个足够大的值。 这是因为，包含航班状态的响应消息通常都相当大，并且可能超出指定的默认消息大小。  
  
    4.  上**安全**选项卡上，执行以下操作：  
  
        1.  有关**安全模式**，选择**传输**。  
  
        2.  有关**传输客户端凭据类型**，选择**基本**。  
  
        3.  下**用户名凭据**框中，单击**编辑**。 在**客户端凭据**对话框中，选择**不使用单一登录**，然后输入用户名和密码从检索到**我的帐户**选项卡后必须登录到[Windows Azure 应用商店](http://go.microsoft.com/fwlink/p/?LinkId=257913)。 凭据列出针对**客户 ID** （用户名称） 和**主帐户密钥**（密码） 标签。  
  
        4.  单击 **“确定”**。  
  
    5.  上**消息**选项卡上，为**禁止显示谓词的正文**，指定你想要去除从请求消息的消息负载的谓词。 对于本教程中，指定为`GET`。 原因是： 美国无线运营商航班延迟 REST 终结点上的 GET 方法调用不需要一个消息有效负载中;REST 资源 URL 是不足以检索信息。 但是，到触发器**WCF WebHttp**使 REST 调用的发送端口，则将删除具有某些消息正文的 dummy 消息。 该发送端口不得将此虚拟消息发送到 REST 终结点，因为如前所述，该终结点不需要消息负载。 因此，在调用 REST 终结点之前, 适配器剥离消息负载中指定的谓词仅的 dummy 消息从**禁止显示谓词的正文**文本框。  
  
    6.  单击**确定**直到您会在发送端口属性对话框中。 从左窗格中，单击**筛选器**，并指定要使用通过接收接收的所有消息的筛选器端口中创建[步骤 1： 配置文件接收位置](../core/step-1-configure-a-file-receive-location.md)。  
  
        |||  
        |-|-|  
        |**属性**|设置为**BTS。ReceivePortName**|  
        |**运算符**|设置为**==**|  
        |**值**|设置为`ReceivePortRestAzureMarketPlace`|  
  
    7.  单击 **“确定”**。  
  
## <a name="see-also"></a>另请参阅  
 [教程 5： 调用 REST 接口使用 BizTalk Server](../core/tutorial-5-invoking-a-rest-interface-using-biztalk-server.md)