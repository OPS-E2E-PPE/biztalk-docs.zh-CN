---
title: 步骤 2c:添加 FILEACT 发送端口为 FileAct 存储和转发 （拉取） 方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8743a868-9625-477b-a7da-673bfa262723
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac2579d61aa20db0dcb445b30ebac1bb429221cd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366023"
---
# <a name="step-2c-add-a-fileact-send-port-for-the-fileact-store-and-forward-pull-scenario"></a>步骤 2c:添加 FILEACT 发送端口为 FileAct 存储和转发 （拉取） 方案
在开始此步骤之前，必须完成[步骤 2B:添加 FILE 发送端口以捕获 sw: handlefilerequest 和 sw: handlesnfrequest 消息 FileAct 存储和转发 （拉取） 方案](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports--get-sw-handlefilerequest-and-sw-handlesnfrequest.md)。  
  
### <a name="to-add-a-fileact-send-port"></a>若要添加 FileACT 发送端口  
  
1.  启动**BizTalk Server 管理**。  
  
2.  在控制台树中，依次展开 BizTalk 组，和你想要创建的发送端口的 BizTalk 应用程序。  
  
3.  右键单击**发送端口**，依次指向**新建**，然后单击**静态要求响应发送端口**。  
  
4.  在中**发送端口属性**窗口中，命名该发送端口， **Tutorial_FA_SendRequest_SnF**。  
  
5.  在中**发送端口属性**窗口中，从**传输类型**下拉列表中，选择**FILEACT**，然后单击**配置**。  
  
6.  在中**FILEACT 传输属性**对话框框中，执行以下操作：  
  
    |**使用此**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**密码**|根据压降连接需要设置密码。|  
    |**用户名**|根据压降连接需要设置的用户名。|  
    |**适配器模式**|从下拉列表中，选择**存储和转发**。|  
    |**不可否认指示器**|从下拉列表中，选择**FALSE**。|  
    |**请求类型**|设置为适当\<RequestType\>为基础的 SWIFT 应用预配的字符串。|  
    |**RequestCrypto**|从下拉列表中，选择**FALSE**。|  
    |**请求者**|设置为适当\<请求程序\>为基础的 SWIFT 应用预配的字符串。|  
    |**响应方**|设置为适当\<响应方\>字符串。|  
    |**服务名称**|设置为适当 **\<服务名称\>** 。|  
    |**确认指示器**|从下拉列表中，选择**FALSE**。|  
    |**事件终结点**|从下拉列表中，选择**FALSE**。|  
    |**文件压缩**|从下拉列表中，选择**None**。|  
    |**物理文件夹名称**|键入 C:\SWIFTAdapterTutorial\Fileact\ClientLocation。|  
    |**传输终结点**|键入压降路由组的相应终结点。 此值应与配置中压降 SNL 终结点匹配。|  
    |**ServiceProfile**|从下拉列表中，选择**事务计数**。|  
    |**送达通知**|从下拉列表中，选择**FALSE**。|  
    |**通知队列**|键入基于 SWIFT 与预配的队列名称。|  
  
    > [!NOTE]
    >  如果要传输消息的事务计数，服务配置文件将模式设置为"事务计数"FileAct 发送端口。  
  
7.  单击“确定”  。  
  
8.  在中**发送端口属性**窗口中，执行以下操作：  
  
    |**使用此**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**发送处理程序**|从下拉列表中，选择**FileActHost**。|  
    |**发送管道**|从下拉列表中，选择**XMLTransmit**。|  
    |**接收管道**|从下拉列表中，选择**XMLReceive**。|  
  
9. 在中**发送端口属性**窗口，然后在**筛选器**选项卡上，执行以下操作：  
  
    |**使用此**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**属性**|从下拉列表中，选择**BTS。ReceivePortName**。|  
    |**“运算符”**|从下拉列表中，选择 **==** 。|  
    |**ReplTest1**|类型**Tutorial_IA_InputRequest_SnF**。|  
    |**分组依据**|保留默认值。|  
  
10. 单击“确定”  。  
  
## <a name="see-also"></a>请参阅  
 [步骤 2A:为 FileAct 存储和转发 （拉取） 方案添加文件接收位置](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-fileact-store-and-forward-scenario.md)   
 [步骤 2B:添加 FILE 发送端口以捕获 sw: handlefilerequest 和 sw: handlesnfrequest 消息 FileAct 存储和转发 （拉取） 方案](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports--get-sw-handlefilerequest-and-sw-handlesnfrequest.md)