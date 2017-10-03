---
title: "如何创建发送 Port1 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating send ports
- send ports, creating
ms.assetid: bf32e9f5-ebed-43d2-b9a9-6ab91925d973
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61c82b199f7b8686556f2cbb53a90b0d4b59536e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-a-send-port"></a>如何创建发送端口
使用下列过程来创建 JD Edwards EnterpriseOne 的 BizTalk Server 的发送端口。  
  
### <a name="to-create-a-send-port"></a>创建发送端口的步骤  
  
1.  右键单击“发送端口”节点。  
  
2.  单击**添加发送端口**。  
  
3.  在**创建新发送端口**对话框中，选择**静态请求-响应端口**从**指定的一种发送端口**列表，然后单击**确定**.  
  
     **静态请求-响应发送端口属性**窗口随即打开。  
  
4.  例如，键入发送端口的名称`SSOSendToJDEEntOne`。  
  
5.  单击**传输**的左窗格中。  
  
6.  单击**传输类型**，然后选择**JDEEntOne**。  
  
7.  选择**地址 (URI)**，然后单击省略号 （…） 按钮。  
  
     博士 Edwards EnterpriseOne**传输属性**对话框随即出现。  
  
8.  类型`myJDEEntOneSSO`为**逻辑系统名称**。  
  
9. 选择**是**为**使用 SSO**。  
  
10. 在下拉列表中，选择您创建代表 JD Edwards EnterpriseOne 系统的单一登录 (SSO) 关联应用程序。  
  
     单击**确定**以确认你输入的信息。  
  
## <a name="see-also"></a>另请参阅  
 [创建关联应用程序](../core/creating-affiliate-applications4.md)   
 [使用单一登录](../core/using-single-sign-on1.md)