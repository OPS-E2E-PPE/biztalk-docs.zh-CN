---
title: "故障排除 Adapter3 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapters [JD Edwards OneWorld adapters], connecting [Oracle databases]
- JD Edwards OneWorld adapters, troubleshooting
- troubleshooting [JD Edwards OneWorld adapters]
- adapters [JD Edwards OneWorld adapters], troubleshooting
- Oracle databases, connecting [JD Edwards OneWorld adapters]
ms.assetid: 2dd6a951-f113-4f43-b43f-057a239d05c4
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15197bcdc84e813d31a8d5292f5559aca1f8ae01
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
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
 [如何为博士 Edwards OneWorld 创建发送端口](../core/how-to-create-send-ports-for-jd-edwards-oneworld.md)   
 [故障排除博士 Edwards OneWorld](../core/troubleshooting-jd-edwards-oneworld.md)