---
title: "PeopleSoft 传输属性对话框中 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PeopleSoft
helpviewer_keywords: PeopleSoft Transport Properties dialog box
ms.assetid: 660f0a0b-e076-4f4e-8b2a-6d976acfc5ce
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50362e60b982a2d304efea8c26f58019148e5c16
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="peoplesoft-transport-properties-dialog-box"></a>PeopleSoft 传输属性对话框
使用 PeopleSoft 的“传输属性”对话框设置适配器所需的属性。  
  
|使用此选项|执行的操作|  
|--------------|----------------|  
|**适配器所需的属性**||  
|应用程序服务器路径|键入 PeopleSoft 服务器的路径 (例如， `//psserver.domain.com:9000`)。|  
|JAVA_HOME|键入 JAVA_HOME 位置的名称 (例如， `<drive:>\jdk1.4.2_08`)。|  
|密码|键入此用户的密码。|  
|PeopleSoft 8.x JAR 文件|键入 PeopleSoft JAR 文件的位置的路径 (例如， `<drive:>\JAR_FILES\Peoplesoft_8.4\psjoa.jar`)。|  
|用户名|键入用户的名称，然后单击**确定**。|  
|**其他参数**||  
|数据库日期格式|键入要在其中显示的日期的格式 (例如，**YYYY-月-日**)。<br /><br /> 日期用作键时有不同的格式。|  
|**并发控制**||  
|最大并发调用|键入数字值**最大并发调用**。 此数字表示并发调用的最大数量，例如 200。<br /><br /> 此字段的默认值为 -1，意味着未进行任何保护。|  
|**连接**||  
|最大会话数|键入一个数字以表示最大会话数。<br /><br /> 默认连接次数为 40。|  
|**刷新代理**||  
|刷新代理|选择**是**为**刷新代理**强制 runtimeagent.exe 以及要在需要时自动重新启动 browsingagent.exe 过程。<br /><br /> 例如，您希望进程在出现以下情况时自动重新启动：丢失了与服务器的连接；或者如果向服务器中添加了内容，但是由于它没有显示在适配器向导中而无法选择它。|  
|**单一登录**||  
|关联应用程序|仅当使用单一登录 (SSO) 时，才可以从列表中选择关联应用程序。|  
|使用 SSO|选择**是**如果你使用 SSO; 密码不需要在这种情况下。 **注意：**如果你已输入了密码，并且你想要使用单一登录，右键单击密码字段，然后选择**废除密码**。|  
  
## <a name="see-also"></a>另请参阅  
 [用于 PeopleSoft 企业的 BizTalk Adapter 的用户界面参考](../core/ui-reference-for-biztalk-adapter-for-peoplesoft-enterprise.md)