---
title: JD Edwards EnterpriseOne 传输属性对话框 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- JDE
helpviewer_keywords:
- Transport Properties dialog box [JD Edwards EnterpriseOne adapters
ms.assetid: 6a37eeb2-af91-4f58-9699-7a7cbe296862
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0110e973f944814b481d0588fa508dce9b53f14f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329521"
---
# <a name="jd-edwards-enterpriseone-transport-properties-dialog-box"></a>“JD Edwards EnterpriseOne 传输属性”对话框
使用 JD Edwards EnterpriseOne 传输属性对话框设置适配器所需属性。  
  
|使用此选项|执行的操作|  
|--------------|----------------|  
|**适配器必需属性**||  
|主机|键入主机服务器计算机的名称 (例如， `actsvr1`)。<br /><br /> -或-<br /><br /> 键入计算机的 IP 地址 (例如， `123.456.0.789`)。|  
|JAVA_HOME|键入 JDK 安装的完整路径 （例如，<br /><br /> `C:\jdk1sdk1.4.2_07`).|  
|JDEdwards 环境|在 JD Edwards EnterpriseOne 中键入环境的名称 (例如， `DV7333`)。<br /><br /> DV7333 是开发环境中; 的公用名PY7333 是原型环境：而 PD7333 是生产环境。|  
|JDEdwards JAR 文件|输入每个 JAR 文件的完整路径和文件名称：<br /><br /> -   Connector.jar<br />-   Kernel.jar<br />-   JDEJAccess.jar<br /><br /> 必须用分号 （;） 分隔每个 jar 文件无空格 (例如：<br /><br /> `<c:>\Connector.jar;<c:>\Kernel.jar;`).|  
|Password|键入用户密码。 如果做不 useSingle 单一登录 (SSO)，则必须设置凭据参数，用于访问服务器系统的 JD Edwards EnterpriseOne 的 BizTalk 适配器。 密码对应于用户名称。 密码确定授予访问数据库时的权限。|  
|Port|键入数字标识符的发送或接收端口 (例如， `6009`)。|  
|用户名|键入在用户的名称，然后单击**确定**。|  
|**启动数据源所需的属性**||  
|数据源名称|键入数据源的名称。 此名称是必需的所有数据类型。|  
|数据库所有者|键入数据库所有者的名称|  
|数据库服务器名称|键入数据库服务器的名称|  
|数据库服务器端口|键入数据库服务器端口的标识编号。|  
|数据库类型|键入数据库类型的单个字符。 例如：<br /><br /> **我**-iSeries<br /><br /> **O** - Oracle<br /><br /> **S** -SQL Server<br /><br /> **L** -SQL Server OLEDB<br /><br /> **W** - UDB|  
|物理数据库名称|键入物理数据库的名称。 此名称是必需的所有数据库类型。|  
|**并发控制**||  
|最大并发调用数|键入用于值的数值**最大并发调用**。 此数字表示的最大并发调用数，例如， **10**。<br /><br /> 此字段的默认值为 5。|  
|**刷新代理**||  
|刷新代理|选择**是**有关**刷新代理**以强迫 runtimeagent.exe 和 browsingagent.exe 进程在需要时自动重新启动。<br /><br /> 例如，您希望自动重新启动它将失去与服务器的连接，或者如果将内容添加到服务器并且不会出现在 Microsoft 适配器向导中选择的过程。|  
|**安全服务器**||  
|安全服务器名称|键入安全服务器的名称。 此字段是可选的默认为 JD Edwards 服务器主机。|  
|服务名称连接|键入安全服务器和对象配置映射 (OCM) 使用的端口号。 默认值为 JD Edwards 服务器端口。|  
|**单一登录**||  
|关联应用程序|仅当使用单一登录 (SSO)，请从下拉列表中选择关联应用程序。|  
|使用 SSO|选择**是**如果您使用的 SSO; 密码则不需要在这种情况下。|  
  
## <a name="see-also"></a>请参阅  
 [用于 JD Edwards EnterpriseOne 的 BizTalk 适配器中的安全性](../core/security-in-biztalk-adapter-for-jd-edwards-enterpriseone.md)   
 [创建关联应用程序](../core/creating-affiliate-applications4.md)   
 [用于 JD Edwards EnterpriseOne 的 BizTalk 适配器的用户界面参考](../core/ui-reference-for-biztalk-adapter-for-jd-edwards-enterpriseone.md)