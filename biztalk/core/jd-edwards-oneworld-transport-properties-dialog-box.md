---
title: 博士 Edwards OneWorld 传输属性对话框中 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- JDEOneWorld
helpviewer_keywords:
- Transport Properties dialog box [JD Edwards OneWorld adapters]
ms.assetid: 34d6b5d0-4bd9-4522-a540-8415d3143762
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 625479ef124aad6d7c0b10cde34b45a142ff9f90
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="jd-edwards-oneworld-transport-properties-dialog-box"></a>“JD Edwards OneWorld 传输属性”对话框
使用 JD Edwards OneWorld 的“传输属性”对话框设置适配器所需的属性。  
  
|使用此选项|执行的操作|  
|--------------|----------------|  
|**适配器所需的属性**||  
|主机|键入在主机服务器计算机的名称 (例如， `actsvr1`)。<br /><br /> -或-<br /><br /> 键入计算机的 IP 地址 (例如， `123.456.0.789`)。|  
|JAVA_HOME|键入你的 JDK 安装的完整路径。|  
|JDEdwards 环境|键入博士 Edwards OneWorld 环境的名称 (例如， `DV7333`)。<br /><br /> DV7333 是开发环境的公用名，PY7333 是原型环境的公用名，PD7333 是生产环境的公用名。|  
|JDEdwards JAR 文件|输入每个 JAR 文件的完整路径和文件名：<br /><br /> -Connector.jar<br />-Kernel.jar<br />-JDEJAccess.jar<br />-BTSLIBInterop.jar<br /><br /> 必须使用分号 （;） 和没有空间分隔每个 jar 文件 (例如， `<c:>\Connector.jar;<c:>\Kernel.jar;`)。|  
|密码|键入用户密码。 如果未使用单一登录 (SSO)，则必须为用于 JDEdwards OneWorld 的 BizTalk 适配器设置凭据参数，以便能够访问服务器系统。 密码对应于用户名。 密码决定您被授予访问数据库时的特权。|  
|端口|键入数字标识符的发送或接收端口 (例如， `6009`)。|  
|用户名|键入在用户的名称，然后单击**确定**。|  
|最大并发调用|键入数字值**最大并发调用**。 此数字表示的最大并发调用数，例如， **10**。<br /><br /> 此字段的默认值是**5**，这意味着无保护时发生。|  
|刷新代理|选择**是**为**刷新代理**强制 runtimeagent.exe 以及要在需要时自动重新启动 browsingagent.exe 过程。<br /><br /> 例如，您希望进程在出现以下情况时自动重新启动：丢失了与服务器的连接；或者向服务器中添加了内容，但是由于它没有显示在 Microsoft 适配器向导中而无法选择它。|  
|关联应用程序|仅当使用 SSO 时才从列表中选择关联应用程序。|  
|使用 SSO|选择**是**如果你使用 SSO; 密码不需要在这种情况下。|  
  
## <a name="see-also"></a>另请参阅  
 [适配器中的安全](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)   
 [创建关联应用程序](../core/creating-affiliate-applications3.md)   
 [用于 JDE OneWorld 的 BizTalk 适配器用户界面参考](../core/ui-reference-for-biztalk-adapter-for-jde-oneworld.md)