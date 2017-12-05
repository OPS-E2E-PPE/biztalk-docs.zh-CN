---
title: "第 1 课： 添加平面文件接收端口和位置 |Microsoft 文档"
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
- receive ports, creating
- creating, receive ports
ms.assetid: 881f58d8-f541-4a85-b534-cb1ca627c002
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9856e0da6e8a4bc958b5fe08e0e1b5e87494531b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="lesson-1-adding-flat-file-receive-port-and-location"></a>第 1 课： 添加平面文件接收端口和位置
接收端口始终具有添加接收端口时，必须配置关联的接收位置。 接收位置定义传入的消息并使用来处理该消息的管道的特定地址。  
  
### <a name="to-add-a-receive-port"></a>若要添加接收端口  
  
1.  在 BizTalk Server 管理控制台中，右键单击**接收端口**，指向**新建**，然后单击**单向接收端口**。  
  
2.  在接收端口属性对话框中，在**名称**框中，键入**MT103_FlatFile_ReceivePort**。  
  
3.  单击**应用**以绑定端口，然后单击**确定**。  
  
4.  在 BizTalk Server 管理控制台中，右键单击**接收位置**，指向**新建**，然后单击**单向接收位置**。  
  
5.  在选择接收端口对话框中，单击**MT103_FlatFile_ReceivePort**，然后单击**确定**。  
  
6.  在接收位置属性对话框中，在**名称**框中，键入**MT103_FlatFile_ReceiveLocation**。  
  
7.  在**传输**部分中，为**类型**文本框中，单击下拉列表中，，然后选择**文件**。  
  
8.  单击**配置**类型下拉列表右侧的按钮。  
  
9. 在文件传输属性对话框中，单击**浏览**。  
  
10. 在浏览文件夹对话框中，移动到**\<驱动器\>: \Labs\Inbound**文件夹，，然后单击**新建文件夹**。  
  
11. 创建**FlatFile**文件夹中的**\<驱动器\>: \Labs\Inbound**，然后单击**确定**。  
  
12. 在**文件掩码**框中，键入 **\*.txt**，然后单击**确定**。  
  
13. 在接收位置属性对话框中，确保**BizTalkServerApplication**为输入**接收处理程序**框。  
  
14. 有关**接收管道**框中，选择**MT103ReceivePipeline**从下拉列表。  
  
15. 单击**应用**，然后单击**确定**。  
  
16. 在 BizTalk Server 管理控制台中，单击**接收位置**，右键单击**MT103_FlatFile_ReceiveLocation**，然后单击**启用**。  
  
 继续执行[第 2 课： 添加 XML 发送端口](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-an-xml-send-port.md)。