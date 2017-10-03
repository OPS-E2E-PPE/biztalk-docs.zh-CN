---
title: "创建 A4SWIFT 接收位置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive locations, creating
- creating, receive locations
ms.assetid: 712cf42f-8d71-47e9-b2bf-3da158b74fe4
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3f0835c6d83efc9db91f5c1d63e91f4c143399d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="creating-an-a4swift-receive-location"></a>创建 A4SWIFT 接收位置
你必须创建[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]接收位置来启用从 SWIFT 通过网络接收到消息[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]下, 图中所示。 接收位置接收平面文件消息的入站的文件文件夹。  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-receive-location-configuration.gif "A4SWIFT_Receive_Location_Configuration")  
  
 **摘要**  
  
 创建和绑定单向接收端口，然后创建并启用的接收位置具有以下属性和组件：  
  
|属性/组件|设置|  
|--------------------------|-------------|  
|接收端口|单向端口|  
|传输类型|FILE|  
|地址 URI|你想要接收消息的文件夹名称|  
|文件掩码|\*.*\<扩展 >*，其中\<*扩展*> 是的传入的扩展名为平面文件消息|  
|接收处理程序|BizTalkServerApplication|  
|接收管道|[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]接收你创建的管道|  
  
### <a name="to-add-the-receive-port-and-location"></a>若要添加的接收端口和位置  
  
1.  启动**BizTalk Server 管理**控制台。  
  
    > [!NOTE]
    >  BizTalk Server 管理控制台也可以打开从 Visual Studio 中通过单击**BizTalk Server 管理**中**工具**菜单。  
  
2.  在管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开**BizTalk应用程序 1**。  
  
3.  右键单击**接收端口**，指向**新建**，然后单击**单向接收端口**。  
  
4.  在接收端口属性对话框中，在**名称**框中，键入接收端口的名称。  
  
5.  单击**应用**以绑定端口，然后单击**确定**。  
  
6.  右键单击**接收位置**，指向**新建**，然后单击**单向接收位置**。  
  
7.  在选择接收端口对话框框中，单击你刚接收端口创建，然后单击**确定**。  
  
8.  在接收位置属性对话框中，在**名称**框中，键入接收位置的名称。  
  
9. 在**传输**部分中，为**类型**文本框中，单击下拉列表中，，然后选择**文件**。  
  
10. 单击**配置**类型下拉列表右侧的按钮。  
  
11. 在文件传输属性对话框中，单击**浏览**。 移动到文件夹，你想要接收消息。 单击 **“确定”**。  
  
    > [!NOTE]
    >  如果此文件夹不存在，则可以创建使用**新建文件夹**命令。  
  
12. 在文件传输属性对话框中，在**文件掩码**框中，输入  **\*。\<*扩展*>**，其中\<*扩展*> 是的传入的扩展名平面文件消息，例如**.txt**。 单击 **“确定”**。  
  
13. 在接收位置属性对话框中，确保**BizTalkServerApplication**为输入**接收处理程序**框。  
  
14. 有关**接收管道**框中，从下拉列表中选择你自定义接收管道。  
  
15. 单击**应用**，然后单击**确定**。  
  
16. 在 BizTalk Server 管理控制台中，单击**接收位置**，右键单击你刚接收位置创建，然后单击**启用**。  
  
    > [!NOTE]
    >  启用接收位置后，BizTalk 主动轮询文件文件夹。