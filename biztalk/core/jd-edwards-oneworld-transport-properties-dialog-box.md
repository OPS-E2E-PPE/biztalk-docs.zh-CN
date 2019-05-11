---
title: JD Edwards OneWorld 传输属性对话框 |Microsoft Docs
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
ms.openlocfilehash: 7fc782c8067cb55278878d3af7525d47b517a349
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380694"
---
# <a name="jd-edwards-oneworld-transport-properties-dialog-box"></a>JD Edwards OneWorld 传输属性对话框
使用 JD Edwards OneWorld 传输属性对话框设置适配器所需属性。  
  
|使用此选项|执行的操作|  
|--------------|----------------|  
|**适配器必需属性**||  
|主机|键入主机服务器计算机的名称 (例如， `actsvr1`)。<br /><br /> -或者-<br /><br /> 键入计算机的 IP 地址 (例如， `123.456.0.789`)。|  
|JAVA_HOME|键入 JDK 安装的完整路径。|  
|JDEdwards 环境|在 JD Edwards OneWorld 中键入环境的名称 (例如， `DV7333`)。<br /><br /> DV7333 是开发环境的公用名，PY7333 是原型环境和 PD7333 是生产环境。|  
|JDEdwards JAR 文件|输入每个 JAR 文件的完整路径和文件名称：<br /><br /> -   Connector.jar<br />-   Kernel.jar<br />-   JDEJAccess.jar<br />-   BTSLIBInterop.jar<br /><br /> 必须用分号 （;） 分隔每个 jar 文件无空格 (例如， `<c:>\Connector.jar;<c:>\Kernel.jar;`)。|  
|Password|键入用户密码。 如果不使用单一登录 (SSO)，则必须设置凭据参数，以便能够访问服务器系统的 JDEdwards OneWorld 的 BizTalk 适配器。 密码对应于用户名称。 密码确定授予访问数据库时的权限。|  
|Port|键入数字标识符的发送或接收端口 (例如， `6009`)。|  
|“用户名”|键入在用户的名称，然后单击**确定**。|  
|最大并发调用数|键入用于值的数值**最大并发调用**。 此数字表示的最大并发调用数，例如， **10**。<br /><br /> 此字段的默认值是**5**，这意味着无保护时发生。|  
|刷新代理|选择**是**有关**刷新代理**以强迫 runtimeagent.exe 和 browsingagent.exe 进程在需要时自动重新启动。<br /><br /> 例如，您希望自动重新启动它将失去与服务器的连接，或者如果将内容添加到服务器并且不会出现在 Microsoft 适配器向导中选择的过程。|  
|关联应用程序|仅当使用 SSO，请从列表中选择关联应用程序。|  
|使用 SSO|选择**是**如果您使用的 SSO; 密码则不需要在这种情况下。|  
  
## <a name="see-also"></a>请参阅  
 [适配器中的安全性](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)   
 [创建关联应用程序](../core/creating-affiliate-applications3.md)   
 [用于 JDE OneWorld 的 BizTalk 适配器用户界面参考](../core/ui-reference-for-biztalk-adapter-for-jde-oneworld.md)