---
title: PeopleSoft 传输属性对话框 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- PeopleSoft
helpviewer_keywords:
- PeopleSoft Transport Properties dialog box
ms.assetid: 660f0a0b-e076-4f4e-8b2a-6d976acfc5ce
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8134f51cd6ac0ef90b2ef204b4e6c6ee38f7b6b0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65322171"
---
# <a name="peoplesoft-transport-properties-dialog-box"></a>PeopleSoft 传输属性对话框
使用 PeopleSoft 传输属性对话框设置适配器所需属性。  
  
|使用此选项|执行的操作|  
|--------------|----------------|  
|**适配器必需属性**||  
|应用程序服务器路径|键入 PeopleSoft 服务器的路径 (例如， `//psserver.domain.com:9000`)。|  
|JAVA_HOME|键入 JAVA_HOME 位置的名称 (例如， `<drive:>\jdk1.4.2_08`)。|  
|Password|键入此用户的密码。|  
|PeopleSoft 8.x JAR 文件|键入 PeopleSoft JAR 文件的位置的路径 (例如， `<drive:>\JAR_FILES\Peoplesoft_8.4\psjoa.jar`)。|  
|“用户名”|键入在用户的名称，然后单击**确定**。|  
|**其他参数**||  
|数据库日期格式|键入要在其中显示日期的格式 (例如，**年-月-日**)。<br /><br /> 日期具有不同的格式时用作键。|  
|**并发控制**||  
|最大并发调用数|键入用于值的数值**最大并发调用**。 此数字表示的最大并发调用，例如，200 数。<br /><br /> 默认值为此字段为-1，这意味着无保护时发生。|  
|**“连接”**||  
|最大会话数|键入一个数字以表示最大会话数。<br /><br /> 默认连接数为 40。|  
|**刷新代理**||  
|刷新代理|选择**是**有关**刷新代理**以强迫 runtimeagent.exe 和 browsingagent.exe 进程在需要时自动重新启动。<br /><br /> 例如，您希望自动重新启动它将失去与服务器的连接，或者如果将内容添加到服务器并且不会出现在所选内容在适配器向导中的过程。|  
|**单一登录**||  
|关联应用程序|仅当使用单一登录 (SSO)，请从列表中选择关联应用程序。|  
|使用 SSO|选择**是**如果您使用的 SSO; 密码则不需要在这种情况下。 **注意：** 如果您已经输入了密码，并且你想要使用单一登录，请右键单击字段并选择的密码**置空密码**。|  
  
## <a name="see-also"></a>请参阅  
 [PeopleSoft Enterprise 的 BizTalk 适配器用户界面参考](../core/ui-reference-for-biztalk-adapter-for-peoplesoft-enterprise.md)