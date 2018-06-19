---
title: 步骤 4： 创建用于接受批处理消息接收端口 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a37eb334-c4ae-40d1-a433-bf0ab39c0765
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 56d1aa54639263e6741c6df89c3888b9b4120515
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207605"
---
# <a name="step-4-create-a-receive-port-for-accepting-the-batch-message"></a>步骤 4： 创建用于接受批处理消息接收端口
在此步骤中，创建并配置一个端口用于接收传入的批。  
  
 创建请求-响应 （双向） 接收端口，因为此情形包括生成的应用程序的接受批处理中的单个消息的确认。 在双向模式下，MLLP 接收适配器将不接受新的传入消息，直到接收管道都生成前面的消息，确认 (ACK)。  
  
## <a name="create-the-receive-port-for-accepting-the-batch-message"></a>创建用于接受批处理消息的接收端口  
  
1.  打开**BizTalk Server 管理**，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开**BizTalk 应用程序 1**。  
  
    > [!NOTE]
    >  BizTalk Server 管理控制台也可以打开从 Visual Studio 中通过单击**BizTalk Server 管理**中**工具**菜单。  
  
2.  右键单击**接收端口**，选择**新建**，然后选择**请求响应接收端口**。  

3.  有关**名称**，输入**Tutorial_2WayReceive**。  

4.  选择**应用**要将该端口绑定，然后选择**接收位置**。  
  
5.  选择**新**。  

6.  有关**名称**，输入**Tutorial_2WayReceive**。

7. 在**传输**部分中，选择**类型**，然后选择**MLLP**从下拉列表。  
  
8. 选择 **“配置”**。 在**MLLP 传输属性**，配置以下内容，，然后选择**确定**。  

    |使用此选项|执行的操作|  
    |---|---|  
    |**连接重试时间 （秒）**|新开头[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]。 <br/><br/>在尝试重新连接被删除或已关闭连接之前等待的时间上限。 可用**连接由**设置为**本地**。<br/><br/>默认值为 20 秒。|
    |**由启动的连接**| 新开头[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]。 <br/><br/>输入**本地**对于 MLLP 收到位置以启动远程的 LOB 服务器的连接。 这是新的选项。<br/><br/>输入**远程**对于 MLLP 收到位置继续侦听从远程 LOB 服务器的连接。 这是向后兼容默认选项。<br/><br/>默认值为远程。| 
    |**连接名称**|输入**2Way**。|  
    |**主机名**|特定于[!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)]和较旧版本。 <br/><br/>输入**localhost**。|  
    |**本地主机名**|新开头[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]。 <br/><br/>输入的 DNS 名称或 IP 地址的本地[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]。 你也可以输入**localhost**。|  
    |**端口**|特定于[!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)]和较旧版本。 <br/><br/>设置为**21000**。|  
    |**本地端口**|新开头[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]。 <br/><br/>输入本地主机连接的 TCP 端口号。 适用时，才**连接由**是**远程**。 <br/><br/>设置为**21000**。|
    |**远程主机**|新开头[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]。 <br/><br/>输入的 DNS 名称或远程的 LOB 服务器 IP 地址。 可用**连接由**设置为**本地**。|  
    |**远程端口**|新开头[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]。 <br/><br/>输入对远程主机连接的 TCP 端口号。 可用**连接由**设置为**本地**。<br/><br/>设置为**21000**。|  

9. 在接收位置属性中，选择以下项：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**接收处理程序**|选择**BizTalkServerApplication**从下拉列表|  
    |**接收管道**|选择**BTAHL72XPipelines.BTAHL72XReceivePipeline**|  
    |**发送管道**|选择**BTAHL72XPipelines.BTAHL72XSendPipeline**|  

11. 单击“确定”保存更改。  
  
12. 启用接收位置你刚刚创建，请右键单击它，并选择**启用**。  
  
## <a name="next-step"></a>下一步
[步骤 5： 创建发送端口将消息传递](../../adapters-and-accelerators/accelerator-hl7/step-5-create-a-send-port-to-deliver-messages.md)