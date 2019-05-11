---
title: 添加 MX 接收端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4818d6af-df1d-481e-becf-1af633735248
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d95c9b97b18e20e2a852c5a1507d1110733e481b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378716"
---
# <a name="adding-mx-receive-port"></a>添加 MX 接收端口
**若要添加 MX 接收端口：**  
  
1.  启动**BizTalk Server 管理**控制台。  
  
2.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开**BizTalk 应用程序 1**。  
  
3.  右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口**。  
  
4.  在接收端口属性对话框中的名称框中，键入**MX_ 接收端口**。  
  
5.  单击**Apply**以绑定端口，然后单击**确定**。  
  
6.  右键单击**接收位置**，依次指向**新建**，然后单击**单向接收位置**。  
  
7.  在选择接收端口对话框中，单击**MX_ 接收端口**，然后单击**确定**。  
  
8.  在接收位置属性对话框中的名称框中，键入**MX_ 接收位置**。  
  
9. 在传输部分中，键入文本框中，单击下拉列表中，并选择**文件**。  
  
10. 单击**配置**类型下拉列表右侧的按钮。  
  
11. 在 FILE 传输属性对话框中，单击**浏览**，然后选择文件位置。  
  
12. 在 FILE 传输属性对话框中，确保\*.xml 中的文件掩码框中，输入，然后单击**确定**。  
  
13. 在接收位置属性对话框中，确保接收处理程序框中输入 BizTalkServerApplication。  
  
14. 在接收管道框中，选择**接收管道**（管道项目的部署的接收管道） 从下拉列表中，单击**应用**，然后单击**确定**.  
  
15. 右键单击您刚配置，并单击的位置**启用**。