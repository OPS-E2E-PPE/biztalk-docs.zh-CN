---
title: 第 2 课： 添加平面文件发送端口 |Microsoft Docs
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
ms.openlocfilehash: 90b08dd8083e78d1e7cd98e8e8f705ac23d9bd17
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997318"
---
# <a name="lesson-2-adding-a-flat-file-send-port"></a>第 2 课： 添加平面文件发送端口
在本课程中，你可以配置发送端口和发送位置。 使用发送端口以定义要发送的消息的方式。 您还创建了发送的消息文件文件夹位置。  

### <a name="to-add-a-flat-file-send-port"></a>若要添加平面文件发送端口  

1. 在 BizTalk Server 管理控制台中，右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口**。  

2. 在发送端口属性对话框中，在**名称**框中，键入**MT103_FlatFile_SendPort**。  

3. 在中**传输**部分中，对于**类型**框中，单击下拉列表中，并选择**文件**。  

4. 单击**配置**类型下拉列表右侧的按钮。  

5. 在 FILE 传输属性对话框中，单击**浏览**。  

6. 在浏览文件夹对话框中，转至**\<驱动器\>: \Labs**文件夹，，然后单击**建立新文件夹**。  

7. 创建**出站**中的文件夹**\<驱动器\>: \Labs**，然后单击**确定**。  

8. 在中**文件名**框中，键入 **%MessageID%.txt**，然后单击**确定**。  

9. 在发送端口属性对话框中，单击的下拉列表**发送管道**框，并选择**MT103SendPipeline**。  

10. 在左窗格中，单击**筛选器**，然后执行以下操作：  


    |   使用此选项   |           执行的操作            |
    |--------------|---------------------------------|
    | **属性** | 选择**BTS。ReceivePortName**。 |
    | **“运算符”** |         选择**==**。          |
    |  **ReplTest1**   | 类型**MT103_XML_ReceivePort**。 |


11. 单击**Apply**，然后单击**确定。**  

12. 在中**发送端口**窗格中，右键单击**MT103_FlatFile_SendPort**，然后单击**启动**。  

    请继续执行[模块 5： 添加平面文件接收位置和 XML 发送端口](../../adapters-and-accelerators/accelerator-swift/module-5-adding-a-flat-file-receive-location-and-xml-send-port.md)。