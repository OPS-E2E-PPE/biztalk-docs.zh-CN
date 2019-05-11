---
title: 如何创建发送 Port1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating send ports
- send ports, creating
ms.assetid: bf32e9f5-ebed-43d2-b9a9-6ab91925d973
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a0657f32edfbddd3830605d271daafc632db60d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385566"
---
# <a name="how-to-create-a-send-port"></a>如何创建发送端口
使用以下过程来创建 BizTalk Server 用于 JD Edwards EnterpriseOne 的发送端口。  
  
### <a name="to-create-a-send-port"></a>若要创建的发送端口  
  
1.  右键单击发送端口节点。  
  
2.  单击**添加发送端口**。  
  
3.  在中**创建新发送端口**对话框中，选择**静态要求响应端口**从**指定的发送端口类型**列表，然后单击**确定**.  
  
     **静态要求响应发送端口属性**窗口随即打开。  
  
4.  例如，键入发送端口的名称`SSOSendToJDEEntOne`。  
  
5.  单击**传输**的左窗格中。  
  
6.  单击**传输类型**，然后选择**JDEEntOne**。  
  
7.  选择**地址 (URI)**，然后单击省略号 （...） 按钮。  
  
     JD Edwards EnterpriseOne**传输属性**对话框随即出现。  
  
8.  类型`myJDEEntOneSSO`有关**逻辑系统名称**。  
  
9. 选择**是**有关**使用 SSO**。  
  
10. 在下拉列表中，选择您创建的用于代表 JD Edwards EnterpriseOne 系统的单一登录 (SSO) 关联应用程序。  
  
     单击**确定**以确认您输入的信息。  
  
## <a name="see-also"></a>请参阅  
 [创建关联应用程序](../core/creating-affiliate-applications4.md)   
 [用于 JD Edwards EnterpriseOne 的 BizTalk 适配器中的安全性](../core/security-in-biztalk-adapter-for-jd-edwards-enterpriseone.md)