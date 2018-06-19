---
title: 步骤 5： 创建用于接受其消息接收端口 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interrogative tutorial, receive ports
ms.assetid: c0b311d8-541c-4c21-a514-c93092c36fe2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0df326e3b08438f7a1eb7d3a2df3c5a816e79bc7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207245"
---
# <a name="step-5-create-the-receive-port-for-accepting-his-messages"></a>步骤 5： 创建用于接受其消息接收端口
在此步骤中，你将创建接收端口指定为发送医院信息系统 (HIS) 的传入消息的位置。 使用以下过程来创建用于接受来自使用最小较低层协议 (MLLP) 适配器 ADT 系统的查询响应消息的接收端口。  
  
## <a name="create-the-hisreceiveport-receive-port"></a>创建 HIS_ReceivePort 接收端口  

1.  打开**BizTalk Server 管理**，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开**BizTalk 应用程序 1**。  
  
2.  右键单击**接收端口**，选择**新建**，然后选择**单向接收端口**。   
  
3.  有关**名称**，输入**HIS_ReceivePort**。  

4.  选择**应用**要将该端口绑定，然后选择**接收位置**。  
  
5.  选择**新**。  
  
6.  有关**名称**，输入**HIS_Receive**。  

7. 在**传输**部分中，选择**类型**，然后选择**MLLP**从下拉列表。  
  
8. 选择 **“配置”**。 在**MLLP 传输属性**，配置以下内容，，然后选择**确定**。  

    |使用此选项|执行的操作|  
    |---|---|  
    |**连接重试时间 （秒）**|新开头[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]。 <br/><br/>在尝试重新连接被删除或已关闭连接之前等待的时间上限。 可用**连接由**设置为**本地**。<br/><br/>默认值为 20 秒。|
    |**由启动的连接**| 新开头[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]。 <br/><br/>输入**本地**对于 MLLP 收到位置以启动远程的 LOB 服务器的连接。 这是新的选项。<br/><br/>输入**远程**对于 MLLP 收到位置继续侦听从远程 LOB 服务器的连接。 这是向后兼容默认选项。<br/><br/>默认值为远程。| 
    |**连接名称**|输入**HIS_ReceiveMLLP**。|  
    |**主机名**|特定于[!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)]和较旧版本。 <br/><br/>输入**localhost**。|  
    |**本地主机名**|新开头[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]。 <br/><br/>输入的 DNS 名称或 IP 地址的本地[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]。 你也可以输入**localhost**。|  
    |**端口**|特定于[!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)]和较旧版本。 <br/><br/>设置为**23000**。|  
    |**本地端口**|新开头[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]。 <br/><br/>输入本地主机连接的 TCP 端口号。 适用时，才**连接由**是**远程**。 <br/><br/>设置为**23000**。|
    |**远程主机**|新开头[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]。 <br/><br/>输入的 DNS 名称或远程的 LOB 服务器 IP 地址。 可用**连接由**设置为**本地**。|  
    |**远程端口**|新开头[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]。 <br/><br/>输入对远程主机连接的 TCP 端口号。 可用**连接由**设置为**本地**。<br/><br/>设置为**23000**。|  
    
9. 设置**接收处理者**到**BizTalkServerApplication**。  
  
10. 设置**接收管道**到**BTAHL72XPipelines.BTAHL72XReceivePipeline**。  
  
11. 单击“确定”保存更改。  
  
12. 启用接收位置你刚刚创建，请右键单击它，并选择**启用**。  

## <a name="next-step"></a>下一步  
[步骤 6： 创建发送端口将查询消息传递](../../adapters-and-accelerators/accelerator-hl7/step-6-create-a-send-port-to-deliver-query-messages.md)