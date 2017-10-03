---
title: "添加 MX 发送端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c3ad5d2f-1fcb-49d4-9974-664733308f45
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3cd4c16658ad0ff6b85976fbc6a97c4f397acbdb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="adding-an-mx-send-port"></a>添加 MX 发送端口
**若要添加 MX 发送端口：**  
  
1.  在 BizTalk Server 管理控制台中，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。  
  
2.  在发送端口属性对话框中，在名称框中，键入**MX_SendPort**。  
  
3.  在传输部分中，为类型框中，单击下拉列表中，，然后选择**文件**。  
  
4.  单击**配置**类型下拉列表右侧的按钮。  
  
5.  在文件传输属性对话框中，单击**浏览**。  
  
6.  在中，浏览文件夹对话框中，选择文件位置。  
  
7.  在文件名框中，键入**%MessageID%.xml**，然后单击**确定**。  
  
8.  在发送端口属性对话框中，单击发送管道框中的下拉列表，然后选择管道项目中的发送管道已部署。  
  
9. 在左窗格中，单击**筛选器**，然后指定以下：  
  
    |||  
    |-|-|  
    |属性|Microsoft.Solutions.MX_A4SWIFT。Property.MX_A4SWIFT_Failed|  
    |运算符|选择 = =|  
    |值|False|  
  
10. 单击**应用**，然后单击**确定**。  
  
11. 在发送端口窗格中，右键单击**MX_SendPort**，然后单击**启动**。