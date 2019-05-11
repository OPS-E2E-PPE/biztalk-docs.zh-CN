---
title: 第 2 步：配置双向 Wcf-webhttp 发送端口 |Microsoft Docs
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
ms.openlocfilehash: aa2018b9212ddb1f8a4df8d94d0f48f5bdaf26ec
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392803"
---
# <a name="step-2-configure-a-two-way-wcf-webhttp-send-port"></a>第 2 步：配置双向 Wcf-webhttp 发送端口
在此步骤中配置一个双向**Wcf-webhttp**发送端口来调用 REST 资源 URL 来检索美国航空公司的计划中的延迟。  
  
### <a name="to-configure-wcf-webhttp-send-port"></a>配置 Wcf-webhttp 发送端口  
  
1.  从 BizTalk Server 管理控制台中下, **BizTalk Application 1**节点，右键单击**发送端口**，指向**新建**，然后单击**静态要求响应发送端口**。  
  
2.  在 **“常规”** 选项卡上，请执行下列操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**名称**|类型**SendPortRESTAzureMarketPlace**。|  
    |**类型**|选择**Wcf-webhttp**。|  
    |**发送处理程序**|选择“BizTalkServerApplication” 。|  
    |**发送管道**|选择**PassThruTransmit**。|  
    |**接收管道**|选择**PassThruReceive**。|  
  
     单击**配置**。  
  
3.  从**Wcf-webhttp 传输属性**对话框框中，执行以下操作：  
  
    1.  上**常规**选项卡上，对于**地址 (URI)**，输入`https://api.datamarket.azure.com/oakleaf/US_Air_Carrier_Flight_Delays_Incr/`。  
  
    2.  在常规选项卡上的**HTTP 方法和 URL 映射**，请输入以下命令：  
  
        ```  
        <BtsHttpUrlMapping>  
        <Operation Method="GET" Url="/On_Time_Performance" />  
        </BtsHttpUrlMapping>  
  
        ```  
  
         在这里，**获取**是 HTTP 动词和**On_Time_Performance**追加到基 URI 来构造的唯一资源 URL 来检索航班延误情况。  
         
         > [!TIP] 
         > 在 URL 字段中，任何特殊 XML 字符必须被"转义"。 这可确保这些特殊 XML 字符是处理，并通过端口保留。 例如，`&`特殊字符必须转义为`&amp;`。 
           >
           >从： `Url=”/Customer?{ID}& group=Location”`
           >
           >
           >自： `Url=”/Customer?{ID}&amp;group=Location”`
  
    3.  上**绑定**选项卡上，对于**最大接收消息大小**字段中，选择一个足够大的值。 这是因为包含航班状态的响应消息通常相当大，且可能会超过指定的默认消息大小。  
  
    4.  上**安全**选项卡上，执行以下操作：  
  
        1.  有关**安全模式**，选择**传输**。  
  
        2.  有关**传输客户端凭据类型**，选择**基本**。  
  
        3.  下**用户名凭据**框中，单击**编辑**。 中**客户端凭据**对话框中，选择**不使用单一登录**，然后输入用户名和密码从检索**我的帐户**选项卡后必须登录到[Windows Azure Marketplace](http://go.microsoft.com/fwlink/p/?LinkId=257913)。 对列出这些凭据**Customer ID** （用户名） 和**主帐户密钥**（密码） 标签。  
  
        4.  单击“确定” 。  
  
    5.  上**消息**选项卡上，对于**为谓词取消正文**，指定你想要去除消息负载将请求消息中的谓词。 对于本教程中，指定此方法作为`GET`。 原因是：美国航空公司航班延迟 REST 终结点调用 GET 方法不需要消息负载;REST 资源 URL 足以检索的信息。 但是，以触发**Wcf-webhttp**进行 REST 调用的发送端口，则删除包含某些消息正文的虚拟消息。 发送端口不必须将此虚拟消息发送到 REST 终结点，因为如前面所述，该终结点不需要消息负载。 因此，在调用之前的 REST 终结点，该适配器中去除虚拟消息仅为你在中指定的谓词中的消息有效负载**为谓词取消正文**文本框。  
  
    6.  单击**确定**只有在返回在发送端口属性对话框上。 在左窗格中，单击**筛选器**，并指定筛选器来处理通过接收收到的所有消息端口中创建[步骤 1:配置一个 FILE 接收位置](../core/step-1-configure-a-file-receive-location.md)。  
  
        |||  
        |-|-|  
        |**属性**|设置为**BTS。ReceivePortName**|  
        |**“运算符”**|设置为 **==**|  
        |**ReplTest1**|设置为 `ReceivePortRestAzureMarketPlace`|  
  
    7.  单击“确定” 。  
  
## <a name="see-also"></a>请参阅  
 [教程 5:调用 REST 接口使用 BizTalk Server](../core/tutorial-5-invoking-a-rest-interface-using-biztalk-server.md)