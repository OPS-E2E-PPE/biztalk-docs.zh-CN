---
title: 创建 FRR 接收位置接收来自后端应用程序 |Microsoft Docs
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
ms.openlocfilehash: 12e4e34ef888fa8c6ae7c91cc6b822c164daa9da
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378379"
---
# <a name="creating-the-frr-receive-location-for-receiving-from-the-back-end-application"></a>创建 FRR 接收位置接收来自后端应用程序
若要执行 FIN 响应对帐，需要创建从后端应用程序接收消息的接收位置[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]。  

 **摘要**  

 创建接收位置具有以下属性和组件：  


| 属性 / 组件 |                                                                 设置                                                                 |
|--------------------|-----------------------------------------------------------------------------------------------------------------------------------------|
|    接收端口    |                                                              单向端口                                                               |
|   传输类型   |                                           后端应用程序使用的传输类型                                           |
|    地址 URI     |                                                   根据需要传输类型                                                    |
|  接收处理程序   |                                                        BizTalkServerApplication                                                         |
|  接收管道  | [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]接收的 FRR 创建的管道 |

### <a name="to-add-an-frr-receive-location-for-receiving-from-the-back-end-application"></a>若要添加 FRR 接收位置以便接收来自后端应用程序  

1. 在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**， **BizTalk 组**，**应用程序**，和**BizTalk 应用程序1**节点。  

2. 右键单击**管道**，然后单击**刷新**。  

3. 右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口**。  

4. 在接收端口属性对话框中，在**名称**框中，键入接收端口，例如 FRRBackEndReceivePort 的名称。  

5. 单击**Apply**以绑定端口，然后单击**确定**。  

6. 在管理控制台中，右键单击**接收位置**，依次指向**新建**，然后单击**单向接收位置**。  

7. 在选择接收端口对话框中，选择接收端口刚刚创建，然后依次**确定**。  

8. 在接收位置属性对话框中，在**名称**框中，键入接收位置的名称。  

9. 在中**传输**部分中，对于**类型**文本框中，选择传输类型由后端应用程序。  

10. 单击**配置**。  

11. 在 FILE 传输属性对话框中，填写所需的传输类型的属性，然后单击**确定**。  

12. 在接收位置属性对话框中，对于**接收处理程序**，选择**BizTalkServerApplication**。  

13. 在接收位置属性对话框中，对于**接收管道**，选择[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]接收的 FRR 创建的管道。  

14. 单击**Apply**，然后单击**确定**以关闭**接收位置属性**对话框。  

15. 在 BizTalk 浏览器中，右键单击您刚接收位置创建，然后依次**启用**。
