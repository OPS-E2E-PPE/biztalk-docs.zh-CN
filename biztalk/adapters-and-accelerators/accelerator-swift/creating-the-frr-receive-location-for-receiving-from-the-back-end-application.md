---
title: 创建 FRR 接收位置用于接收从后端应用程序 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, creating
- creating, receive locations
- FRR, creating receive locations
ms.assetid: 78bd8084-ddec-4066-a474-ab5b1a0a849f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46895ff64e6585c8b80979c09874dffb510cf049
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210077"
---
# <a name="creating-the-frr-receive-location-for-receiving-from-the-back-end-application"></a>创建 FRR 接收位置用于接收从后端应用程序
若要执行 FIN 响应对帐，你需要创建一个从后端应用程序置于接收消息的接收位置[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]。  
  
 **摘要**  
  
 创建具有以下属性和组件接收位置：  
  
|属性 / 组件|设置|  
|-------------------------|-------------|  
|接收端口|单向端口|  
|传输类型|后端应用程序使用的传输类型|  
|地址 URI|所必需的传输类型|  
|接收处理程序|BizTalkServerApplication|  
|接收管道|[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]接收为 FRR 创建的管道|  
  
### <a name="to-add-an-frr-receive-location-for-receiving-from-the-back-end-application"></a>若要添加 FRR 接收位置用于接收从后端应用程序  
  
1.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**， **BizTalk 组**，**应用程序**，和**BizTalk 应用程序1**节点。  
  
2.  右键单击**管道**，然后单击**刷新**。  
  
3.  右键单击**接收端口**，指向**新建**，然后单击**单向接收端口**。  
  
4.  在接收端口属性对话框中，在**名称**框中，键入接收端口，如 FRRBackEndReceivePort 的名称。  
  
5.  单击**应用**以绑定端口，然后单击**确定**。  
  
6.  在管理控制台中，右键单击**接收位置**，指向**新建**，然后单击**单向接收位置**。  
  
7.  在选择接收端口对话框中，选择你刚接收端口创建，，然后单击**确定**。  
  
8.  在接收位置属性对话框中，在**名称**框中，键入接收位置的名称。  
  
9. 在**传输**部分中，为**类型**文本框中，选择后端应用程序使用的传输类型。  
  
10. 单击**配置**。  
  
11. 在文件传输属性对话框中，填写所需的传输类型的属性，然后单击**确定**。  
  
12. 在接收位置属性对话框中，为**接收处理程序**，选择**BizTalkServerApplication**。  
  
13. 在接收位置属性对话框中，为**接收管道**，选择[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]接收为 FRR 创建的管道。  
  
14. 单击**应用**，然后单击**确定**关闭**接收位置属性**对话框。  
  
15. 在 BizTalk 资源管理器，右键单击你刚接收位置创建，并依次**启用**。