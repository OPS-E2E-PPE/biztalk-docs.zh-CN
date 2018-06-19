---
title: 第 2 课： 添加平面文件发送端口 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send ports, flat files
- flat files, send ports
- creating, send ports
- send ports, creating
ms.assetid: 33dceb0d-85f5-4e19-820f-cd33b60cd32a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d438a6fa68136b05b358a81f4b026350d92a6af4
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961331"
---
# <a name="lesson-2-adding-a-flat-file-send-port"></a>第 2 课： 添加平面文件发送端口
在本课程中，你可以配置发送端口和发送位置。 发送端口用于定义要发送的消息的方式。 你还创建了发送的消息文件文件夹位置。  
  
### <a name="to-add-a-flat-file-send-port"></a>若要添加的平面文件，将发送端口  
  
1.  在 BizTalk Server 管理控制台中，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。  
  
2.  在发送端口属性对话框中，在**名称**框中，键入**MT103_FlatFile_SendPort**。  
  
3.  在**传输**部分中，为**类型**框中，单击下拉列表中，，然后选择**文件**。  
  
4.  单击**配置**类型下拉列表右侧的按钮。  
  
5.  在文件传输属性对话框中，单击**浏览**。  
  
6.  在浏览文件夹对话框中，移动到**\<驱动器\>: \Labs**文件夹，，然后单击**新建文件夹**。  
  
7.  创建**出站**文件夹中的**\<驱动器\>: \Labs**，然后单击**确定**。  
  
8.  在**文件名**框中，键入 **%MessageID%.txt**，然后单击**确定**。  
  
9. 在发送端口属性对话框中，单击的下拉列表**发送管道**框中，，然后选择**MT103SendPipeline**。  
  
10. 在左窗格中，单击**筛选器**，然后执行以下：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**属性**|选择**BTS。ReceivePortName**。|  
    |**运算符**|选择 **==** 。|  
    |**值**|类型**MT103_XML_ReceivePort**。|  
  
11. 单击**应用**，然后单击**确定。**  
  
12. 在**发送端口**窗格中，右键单击**MT103_FlatFile_SendPort**，然后单击**启动**。  
  
 继续执行[模块 5： 添加平面文件位置和 XML 发送端口接收](../../adapters-and-accelerators/accelerator-swift/module-5-adding-a-flat-file-receive-location-and-xml-send-port.md)。