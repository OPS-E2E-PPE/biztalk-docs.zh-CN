---
title: "解决博士 Edwards OneWorld 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2dd6a951-f113-4f43-b43f-057a239d05c4
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ba2dd62e1d4b6dc0af1845d3129e69dbe582226
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="troubleshooting-the-adapter"></a>故障排除适配器
本主题包含的信息可以帮助您确定和解决使用 JD Edwards OneWorld 的 Microsoft BizTalk 适配器时可能遇到的问题。  
  
## <a name="cannot-use-wildcards-in-send-and-receive-port-properties"></a>不能在发送和接收端口属性中使用通配符  
 JD Edwards One World 的适配器不支持在以下属性字段中使用通配符：  
  
|发送端口属性|接收端口属性|  
|------------------------|---------------------------|  
|用户名|事件文件路径|  
|JDE 环境|事件目标名称前缀|  
|主机||  
|端口||  
|Java_Home||  
|JDE JAR 文件||  
  
## <a name="connecting-to-oracle-database"></a>连接到 Oracle 数据库  
 将 Oracle 数据库与 JD Edwards 一起使用时，必须修改 jdeinterop.ini 文件。 [JDBj-ORACLE] 部分使用单一登录功能定义 Oracle tnsnames 位置；必须使用数据库参数；BizTalk Server 计算机上必须存在 SQLNET.ORA 文件（此文件应包含在 Oracle 客户端）。  
  
 将以下内容添加到 jdeinterop.ini 文件：  
  
1.  在 [JDBj-ORACLE] 下键入：  
  
    ```  
    tns=c:\Oracle\ora92\network\Admin\tnsnames.ora  
    ```  
  
2.  在 [JDBj-BOOTSTRAP DATA SOURCE] 下键入：  
  
    ```  
    database=sys810 [hardcode the database name. This information is available in the JDE.ini file on the JD Edwards computer.]  
    ```  
  
## <a name="see-also"></a>另请参阅  
 [将项目添加到 BizTalk 管理](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)     
 [JD Edwards OneWorld 疑难解答](../core/troubleshooting-jd-edwards-oneworld.md)