---
title: 第 1 步：配置 SWIFT 适配器为 FileAct 存储和转发的请求方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc271544-6bc8-4d62-aba0-3fe3295f2a2a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b3f5d4c6698f06a49b0a5ba2bf6a862a9592a3c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366541"
---
# <a name="step-1-configure-the-swift-adapter-for-fileact-store-and-forward-pull-scenario"></a>第 1 步：配置 SWIFT 适配器为 FileAct 存储和转发的请求方案
完整[准备使用本教程](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md)开始此步骤之前。
  
## <a name="configure-the-swift-adapter"></a>配置 SWIFT 适配器  
  
1.  启动**BizTalk Server 管理**。  
  
2.  在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，展开**平台设置**，展开**适配器**，右键单击**FILEACT**，依次指向**新建**，然后单击**发送处理程序**。  
  
3.  在中**FILEACT – 适配器 HandlerProperties**对话框中，在**常规**选项卡上，从**主机名**下拉列表中，选择**FileActHost**，然后依次**属性**。  
  
4.  在中**FILEACT 传输属性**对话框中，在**属性**选项卡上，执行以下操作：  
  
    |**使用此**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**参数**|键入以下参数:-SagMessagePartner \<Fileact 客户端消息合作伙伴创建在压降\>**注意：** 参数中的客户端是 MessagePartner 压降中配置。|  
    |**加密模式**|从下拉列表中，选择**高级**。|  
    |**FACryptoMode**|从下拉列表中，选择**高级**。|  
    |**LogMessages**|从下拉列表中，选择 **，则返回 TRUE**。 这样，要捕获和跟踪在 BAM 门户中的消息事件。|  
    |**启用**|False|  
    |**事件终结点**|键入相应压降终结点。|  
    |**PhysicalFolderName**|在服务器上键入文件夹的名称。 例如，C:\Fileact\ServerLocation。|  
    |**PollingInterval**|PollingInterval，请键入相应的值。 例如，5。 这指示的间隔 （以秒为单位） 后其检查适配器文件传输状态。|  
    |**密码**|键入用于连接到压降的密码。 有关详细信息，请参阅压降帮助。|  
    |**用户名**|键入用于连接到压降的用户名。|  
  
5.  单击**确定**以关闭 FILEACT 传输属性对话框。  
  
6.  单击**确定**关闭 FILEACT – 适配器处理程序属性对话框。  
  
7.  在消息框中，单击**确定**，然后重新启动 FileAct 主机实例。  
  
8.  重复步骤 1。  
  
9. 在控制台树中，展开**BizTalk Server 管理**，展开**BizTalk**组中，展开**平台设置**，展开**适配器**，选择**FILEACT**，打开**BizTalkServerApplication** ，然后单击**属性**。  
  
10. 在中**FILEACT 传输属性**对话框中，在**属性**选项卡上，执行以下操作：  
  
    |**使用此**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**参数**|键入以下参数:-SagMessagePartner \<Fileact 客户端消息合作伙伴创建在压降\>**注意：** 参数中的客户端是 MessagePartner 压降中配置。|  
    |**加密模式**|从下拉列表中，选择**高级**。|  
    |**LogMessageBody**|从下拉列表中，选择 **，则返回 TRUE**。 这样，要捕获和跟踪在 BAM 门户中的消息事件。 **注意：** 如果设置为 TRUE 时，它将保留消息正文 BizTalk 跟踪数据库中。 但是，出于安全原因，消息正文可以永远不会查看 BAM 门户中。|  
    |**LogMessages**|从下拉列表中，选择 **，则返回 TRUE**。 这样，要捕获和跟踪在 BAM 门户中的消息事件。|  
    |**启用**|**True**|  
    |**事件终结点**|键入相应压降终结点。|  
    |**PhysicalFolderName**|在服务器上键入文件夹的名称。 例如，C:\Fileact\ServerLocation。|  
    |**PollingInterval**|PollingInterval，请键入相应的值。 例如，5。 这指示的间隔 （以秒为单位） 后其检查适配器文件传输状态。|  
    |**密码**|键入用于连接到压降的密码。 有关详细信息，请参阅压降帮助。|  
    |**用户名**|键入用于连接到压降的用户名。|  
  
11. 单击确定关闭 FILEACT 传输属性对话框。  
  
12. 选择将此默认处理程序选项。  
  
13. 单击确定以关闭 FILEACT – 适配器处理程序属性对话框。  
  
14. 在消息框中，单击确定，然后重新启动 BizTalkServerApplication 主机实例。  
  
## <a name="see-also"></a>请参阅  
 [步骤 2：创建发送端口和接收端口为 FileAct 存储和转发 （拉取） 方案](../../adapters-and-accelerators/fileact-interact/step-2-create-send-and-receive-ports-for-fileact-store-and-forward-scenario.md)   
 [步骤 3：创建并将替换为 Fileact 存储和转发 （拉取） 方案的动态发送端口业务流程绑定](../../adapters-and-accelerators/fileact-interact/step-3-create-and-bind-an-orchestration-with-dynamic-send-port-for-file-act.md)   
 [步骤 4：测试 FileAct 存储和转发 （拉取） 端到端方案](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-pull-end-to-end-scenario.md)