---
title: 添加 MX 发送端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c3ad5d2f-1fcb-49d4-9974-664733308f45
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 878353f8082ba7990c6e15bc46876544b83e9508
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378694"
---
# <a name="adding-an-mx-send-port"></a>添加 MX 发送端口
**若要添加 MX 发送端口：**  
  
1.  在 BizTalk Server 管理控制台中，右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口**。  
  
2.  在发送端口属性对话框中，在名称框中键入**MX_SendPort**。  
  
3.  在传输部分的类型框中，单击下拉列表，然后选择**文件**。  
  
4.  单击**配置**类型下拉列表右侧的按钮。  
  
5.  在 FILE 传输属性对话框中，单击**浏览**。  
  
6.  在浏览文件夹对话框中，选择文件位置。  
  
7.  在文件名框中，键入 **%MessageID%.xml**，然后单击**确定**。  
  
8.  在发送端口属性对话框中，单击发送管道框中的下拉列表，然后选择管道项目中的已部署的发送管道。  
  
9. 在左窗格中，单击**筛选器**，然后指定以下：  
  
    |||  
    |-|-|  
    |属性|Microsoft.Solutions.MX_A4SWIFT.Property.MX_A4SWIFT_Failed|  
    |运算符|选择 = =|  
    |ReplTest1|False|  
  
10. 单击**Apply**，然后单击**确定**。  
  
11. 在发送端口窗格中，右键单击**MX_SendPort**，然后单击**启动**。